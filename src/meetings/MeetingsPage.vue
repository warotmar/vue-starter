<template>
    <div>
        <h2>Zajęcia</h2>
		
		

		
		<div v-if="addNew">
        <new-meeting-form @added="addNewMeeting($event)"></new-meeting-form>
		</div>
		
		<div v-else>
		<button @click="enter()">{{ buttonLabelToDisplay }}</button>
		</div>
		
		<div>
		        <meetings-list :meetings="meetings" :user="username"></meetings-list>
				  
		</div>
		

    </div>
</template>

<script>
    import NewMeetingForm from "./NewMeetingForm";
    import MeetingsList from "./MeetingsList";

    export default {
		        props: ['buttonLabel', 'addNew', 'username'],

        components: {NewMeetingForm, MeetingsList},
        data() {
            return {
                meetings: []
            };
        },
		computed: {
            buttonLabelToDisplay() {
                return this.buttonLabel || 'Dodaj nowe spotkanie';
            }
        },
        methods: {
            addNewMeeting(meeting) {
                this.meetings.push(meeting);
				this.addNew = '';
            },
			
            enter() {
                this.addNew = 'true';
            }
        }
    }
</script>
