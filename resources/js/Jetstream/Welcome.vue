<template>
    <div>
        <div class="p-6 sm:px-20 bg-white border-b border-gray-200">
            <div class="text-2xl">
                Welcome to Dashboard
            </div>
            <form @submit.prevent="logout">
                <jet-button>
                    Logout
                </jet-button>
            </form>
        </div>
    </div>
</template>

<script>
    import JetButton from '@/Jetstream/Button';

    export default {
        components: {
            JetButton
        },

        methods: {
            logout() {
                axios.post(route('logout').url()).then(response => {
                    window.location = '/';
                })
            },
        },
    }
</script>