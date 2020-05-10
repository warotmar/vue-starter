<template>
    <table v-if="meetings.length > 0">
        <thead>
        <tr>
            <th>Nazwa spotkania</th>
            <th>Opis</th>
			<th>Uczestnicy</th>
			<th></th>


        </tr>
        </thead>
        <tbody>
        <tr v-for="meeting in meetings" :key="meeting.name">
            <td>{{ meeting.name }}</td>
            <td>{{ meeting.description }}</td>
			<td>
			<ul>
			<li v-for="participant in participants"> {{participant}} </li>
			</ul></td>
			<td>
					<button @click="addParticipant()" v-if="!participants.includes(user)">zapisz się</button> &nbsp;
					<button @click="removeParticipant()" v-if="participants.includes(user)">wypisz się</button> &nbsp;
					<button @click="removeMeeting()" v-if="participants.length === 0">usuń puste wydarzenie</button>
		
			</td>
        </tr>
        </tbody>
    </table>
</template>

<script>
    export default {
        props: ['meetings', 'user'],
		
		data() {
            return {
                participants: []
            };
        },
		
		 methods: {
		 addParticipant() {
			this.participants.push(this.user);
            },
			
		removeParticipant() {
			//this.participants.splice(participants.indexOf(user), 1);
				this.participants.pop();
			},
			removeMeeting() {
            },
            
        }
    }
</script>
