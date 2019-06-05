<template>
    <v-flex sm2 md2 xs12 text-md-center light-blue darken-3 pa-2 sidebar shrink>
        <div class="white round">
            <img src="../../assets/logo.svg" alt="">
        </div>

        <div class="navigation mt-5">
            <v-list class="nav-ul pl-3">
                <v-list-tile><a href="#" class="white--text"><i class="material-icons mr-2">dashboard</i> Dashboard</a></v-list-tile>
                <v-list-tile><a href="#" class="white--text"><i class="material-icons mr-2">shopping_cart</i> Products</a></v-list-tile>
                <v-list-tile><a href="#" class="white--text"><i class="material-icons mr-2">receipt</i> Orders</a></v-list-tile>
                <v-list-tile><a href="#" class="white--text"><i class="material-icons mr-2">insert_chart_outlined</i> Insight</a></v-list-tile>
                <v-list-tile><a href="#" class="white--text"><i class="material-icons mr-2">settings</i> Settings</a></v-list-tile>
            </v-list>
        </div>
        
        <div class="chat-icon">
            <span class="material-icons">forum</span>
        </div>
    </v-flex>
</template>


<script>

export default {
    name: 'Sidebar',
}
    
</script>


<style scoped>
    .sidebar {
        min-height: 100vh !important;
        height: auto !important;
    }
</style>