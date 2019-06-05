<template>
  <v-container fluid pa-0>
      <v-layout row wrap>
          <Sidebar />
          
          <v-flex sm10 md10 xs12 main expand>
            <v-layout row top-nav>
                <v-flex px-3 py-0 xs4>
                    <v-text-field
                      hide-details
                      prepend-icon="search"
                      single-line
                      placeholder="Search"  
                      class="nav-search"
                    ></v-text-field>
                </v-flex>
                <v-flex sm9 md9 xs8 style="text-align: right; padding-top: 10px;">
                    <v-btn flat class="top-nav-link"><span class="material-icons bell">notification_important</span></v-btn> | 
                    <v-menu offset-y>
                        <template v-slot:activator="{ on }">
                          <v-btn flat color="dark" class="top-nav-link" v-on="on">
                            Azeezat
                            <i class="material-icons">expand_more</i>
                            <i class="material-icons">person_pin</i>
                          </v-btn>
                        </template>
                        <v-list>
                            <v-list-tile><a href="#" class="black--text"><i class="material-icons mr-2">insert_chart_outlined</i> Insight</a></v-list-tile>
                            <v-list-tile><a href="#" class="black--text"><i class="material-icons mr-2">settings</i> Settings</a></v-list-tile>
                        </v-list>
                    </v-menu>
                </v-flex>
            </v-layout>
            <!--<v-toolbar pb-0 mb-0 style="background: #fff">
                <v-toolbar-side-icon></v-toolbar-side-icon>
                <v-toolbar-title>
                    <v-text-field
                      hide-details
                      prepend-icon="search"
                      single-line
                      placeholder="Search"  
                    ></v-text-field>
                </v-toolbar-title>
                <v-spacer></v-spacer>
                <v-toolbar-items class="hidden-sm-and-down">
                    <v-btn flat><span class="material-icons">notification_important</span></v-btn>
                    <v-menu offset-y>
                        <template v-slot:activator="{ on }">
                          <v-btn flat color="dark" v-on="on">
                            Azeezat
                            <i class="material-icons">expand_more</i>
                            <i class="material-icons">person_pin</i>
                          </v-btn>
                        </template>
                        <v-list>
                            <v-list-tile><a href="#" class="black--text"><i class="material-icons mr-2">insert_chart_outlined</i> Insight</a></v-list-tile>
                            <v-list-tile><a href="#" class="black--text"><i class="material-icons mr-2">settings</i> Settings</a></v-list-tile>
                        </v-list>
                    </v-menu>
                </v-toolbar-items>
            </v-toolbar>-->
             
             <v-content>
                <v-container grid-list-lg>
                    <v-layout row wrap>
                        <v-flex>
                            <h1 class="pt-0 mt-0 primary--text">Orders</h1>
                        </v-flex>
                        <v-flex sm3 md3>
                           <v-layout row wrap>
                               <v-flex sm6 md6 xs6 pr-0 mr-0>
                                   <v-dialog
                                      ref="dialog"
                                      v-model="modal"
                                      :return-value.sync="date"
                                      persistent
                                      lazy
                                      full-width
                                      width="290px"
                                    >
                                      <template v-slot:activator="{ on }">
                                        <v-text-field
                                          v-model="date"
                                          prepend-icon="event"
                                          readonly
                                          v-on="on"
                                        ></v-text-field>
                                      </template>
                                      <v-date-picker v-model="date" scrollable>
                                        <v-spacer></v-spacer>
                                        <v-btn flat color="primary" @click="modal = false">Cancel</v-btn>
                                        <v-btn flat color="primary" @click="$refs.dialog.save(date)">OK</v-btn>
                                      </v-date-picker>
                                    </v-dialog>
                               </v-flex>
                               <v-flex sm6 md6 xs6>
                                   <v-dialog
                                      ref="dialog"
                                      v-model="modal"
                                      :return-value.sync="date"
                                      persistent
                                      lazy
                                      full-width
                                      width="290px"
                                    >
                                      <template v-slot:activator="{ on }">
                                        <v-text-field
                                          v-model="date"
                                          prepend-icon="minimize"
                                          readonly
                                          v-on="on"
                                        ></v-text-field>
                                      </template>
                                      <v-date-picker v-model="date" scrollable>
                                        <v-spacer></v-spacer>
                                        <v-btn flat color="primary" @click="modal = false">Cancel</v-btn>
                                        <v-btn flat color="primary" @click="$refs.dialog.save(date)">OK</v-btn>
                                      </v-date-picker>
                                    </v-dialog>
                               </v-flex>
                           </v-layout>
                        </v-flex>
                    </v-layout>
                    
                    <v-layout row wrap>
                        <v-flex md4 sm4>
                            <v-card class="pa-4">
                                <p>Number of Orders</p>
                                <v-layout row>
                                    <v-flex md6>
                                        <h2 class="order-sum-head">246</h2>
                                        <span class="red--text order-sum"><i class="material-icons">arrow_downward</i> 13.8%</span>
                                    </v-flex>
                                    <v-flex md6 align-self-baseline>
                                        <v-img src="img/Bar Chart-2.svg" alt="" />
                                    </v-flex>
                                </v-layout>
                            </v-card>
                        </v-flex>
                        
                        <v-flex md4 sm4>
                            <v-card class="pa-4">
                                <p>Completed Orders</p>
                                <v-layout row>
                                    <v-flex md6>
                                        <h2 class="order-sum-head">2543</h2>
                                        <span class="green--text order-sum"><i class="material-icons">arrow_upward</i> 13.8%</span>
                                    </v-flex>
                                    <v-flex md6 align-self-baseline>
                                        <v-img src="img/Bar Chart-1.svg" alt="" />
                                    </v-flex>
                                </v-layout>
                            </v-card>
                        </v-flex>
                        
                        <v-flex md4 sm4>
                            <v-card class="pa-4">
                                <p>Abandoned Orders</p>
                                <v-layout row>
                                    <v-flex md6>
                                        <h2 class="order-sum-head">39</h2>
                                        <span class="red--text order-sum"><i class="material-icons">arrow_downward</i> 13.8%</span>
                                    </v-flex>
                                    <v-flex md6 align-self-baseline>
                                        <v-img src="img/Bar Chart.svg" alt="" />
                                    </v-flex>
                                </v-layout>
                            </v-card>
                        </v-flex>
                    </v-layout>
                    
                    
                    <v-layout class="row wrap">
                        <v-flex md12 sm12>
                            <v-card class="pa-4 mt-4" style="overflow-x: auto">
                                <h3 class=" mt-0 pt-0">Orders History</h3>
                                <table width="100%" class="order-table mt-3">
                                    <thead class="">
                                      <tr>
                                          <th class="text-sm-left grey lighten-3">Order Id</th>
                                          <th class="text-sm-left grey lighten-3">Description</th>
                                          <th class="text-sm-left grey lighten-3">Payment Method</th>
                                          <th class="text-sm-left grey lighten-3">Shipping Method</th>
                                          <th class="text-sm-left grey lighten-3">Order Amount</th>
                                          <th class="text-sm-left grey lighten-3">Date</th>
                                          <th class="text-sm-left grey lighten-3">Status</th>
                                      </tr>
                                    </thead>
                                    <tbody>
                                      <tr v-for="order in orders" :key="order.id">
                                        <td>{{order.id}}</td>
                                        <td class="primary--text">{{order.description}}</td>
                                        <td>{{order.payment}}</td>
                                        <td>{{order.shipping}}</td>
                                        <td>{{order.amount}}</td>
                                        <td>{{order.date}}</td>
                                        <td><button class="round px-3 py-1 white--text" :class="order.status === 0? 'red' :  order.status === 1? 'primary' : 'success'" style="width: 100%">{{order.status === 0? 'Abandoned' :  order.status === 1? 'In transit' : 'Completed'}}</button></td>
                                      </tr>
                                    </tbody>
                                </table>
                            </v-card>
                        </v-flex>
                    </v-layout>
                </v-container>
                 
                 
             </v-content>
              
          </v-flex>
      </v-layout>
  </v-container>
</template>

<script>
import Sidebar from './layouts/Sidebar'
    
export default {
  name: 'Dashboard',
  components: {Sidebar},
  data() {
      return {
        date: new Date().toISOString().substr(0, 10),
        modal: false,
        orders: [
            {
                id: '0001',
                description: 'Drizzle Grey Chambray Mix Women\'s Cabrillo Sneakers',
                payment: 'paystack',
                shipping: 'MAX.NG',
                amount: 'N30,000',
                date: '12/12/2001',
                status: 0, 
            },
            {
                id: '0002',
                description: 'American Eagle Classic Women\'s Bal Sneaker Shoe',
                payment: 'Flutterwave',
                shipping: 'MAX.NG',
                amount: 'N30,000',
                date: '12/12/2001',
                status: 1, 
            },
            {
                id: '0003',
                description: 'American Eagle Classic Women\'s Bal Sneaker Shoe',
                payment: 'Flutterwave',
                shipping: 'MAX.NG',
                amount: 'N30,000',
                date: '12/12/2001',
                status: 2, 
            }
        ]
      }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
