<script lang="ts">
    import Dropdown from "./Dropdown.svelte";
    import { Button, ButtonGroup } from 'flowbite-svelte';

    let username:string = "moss_p"
    let loggedIn:boolean = true
    let isAdmin:boolean = false

    let screeningDropdown = [
        {  text: "Create new screening", type: "button", onClick: () => {console.log("Hello")}},
        {  text: "Commit Current Screening", type: "button", onClick: "commit-screening"},
        {  text: "Reset Current Screening", type: "button", onClick: "reset-screening"}
    ]

    let membershipDropdown = [
        {  text: "Check Member Status", type: "button", onClick: "check-member-status"},
        {  text: "New Member", type: "button", onClick: "new-member"},
    ] 

    let settingsDropdown = [
        {  text: "Single Computer Mode", type: "toggle", value:false},
        {  text: "Hide Unused", type: "toggle", value:false},
        ] 
    let userDropdown = [
        {  text: "Change Username", type: "button"},{ text: "Change Password", type: "button"},
        ] 

</script>


<div class="flex">
  <nav class="flex-row-reverse">
    <ButtonGroup>
    {#if loggedIn == false}
    <Button href="#log-in" >Log In</Button>
    {:else}
	<Button color= "red" href="#log-out" >Log Out</Button>
	<Dropdown objects={userDropdown} user = true>{username}</Dropdown>
    {/if}
    <Dropdown objects={settingsDropdown}>Settings</Dropdown>
	<Dropdown objects={screeningDropdown}>Screening</Dropdown>
    <Dropdown objects={membershipDropdown}>Membership</Dropdown>
    {#if isAdmin == true}
	<button class="float-right text-[#f2f2f2] text-center no-underline text-[17px] px-4 py-3.5 hover:bg-[#ddd] hover:text-[black]"href="#contact">Admin</button>
    {/if}
    </ButtonGroup>
    </nav>
</div>

  