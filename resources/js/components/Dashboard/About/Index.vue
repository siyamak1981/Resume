<template>
   
                       <div class="card card-primary mt-3">
                            <div class="card-header">
                                <h3 class="card-title">About List</h3>
                                <div class="cart-total">
                                    <div class="btn btn-primary float-right">
                                        <router-link
                                            to="/create_about"
                                            class="text-white"
                                            >New</router-link
                                        >
                                    </div>
                                </div>
                            </div>
                            <!-- /.card-header -->
                            <div class="card-body">
                                <div
                                    id="example2_wrapper"
                                    class="dataTables_wrapper dt-bootstrap4"
                                >
                                    <div class="row">
                                        <div class="col-sm-12 col-md-6"></div>
                                        <div class="col-sm-12 col-md-6"></div>
                                    </div>
                                    <div class="row">
                                        <div class="col-sm-12">
                                            <table
                                                id="example2"
                                                class="table table-bordered table-hover dataTable dtr-inline"
                                                role="grid"
                                                aria-describedby="example2_info"
                                            >
                                                <thead>
                                                    <tr role="row">
                                                        <th>Id</th>
                                                        <th>title</th>
                                                        <th>description</th>
                                                        <th>created</th>
                                                        <th>Action</th>
                                                    </tr>
                                                </thead>
                                                <tbody>
                                                    <tr
                                                        role="row"
                                                        class="even"
                                                        v-for="(about,
                                                        index) in getAllAbout"
                                                        :key="about.id"
                                                    >
                                                        <td
                                                            class="sorting_1"
                                                            tabindex="0"
                                                        >
                                                            {{ index + 1 }}
                                                        </td>
                                                        <td>
                                                            {{ about.title }}
                                                        </td>
                                                        <td>
                                                            {{ about.description|sortlength(40, "....")|striphtml }}
                                                        </td>
                                                        <td>
                                                            {{
                                                                about.created_at
                                                                    | timeformat
                                                            }}
                                                        </td>
                                                        <td>
                                                            <router-link :to="`edit_about/${about.id}`">Edit</router-link>
                                                            |
                                                            <a href="" @click.prevent = "deleteAbout(about.id)"
                                                                >Delete</a
                                                            >
                                                        </td>
                                                    </tr>
                                                </tbody>
                                                <tfoot>
                                                    <tr>
                                                        <th>Id</th>
                                                        <th>title</th>
                                                        <th>description</th>
                                                        <th>created</th>
                                                        <th>Action</th>
                                                    </tr>
                                                </tfoot>
                                            </table>
                                        </div>
                                    </div>
                                    <div class="row">
                                        <div class="col-sm-12 col-md-5">
                                            <div
                                                class="dataTables_info"
                                                id="example2_info"
                                                role="status"
                                                aria-live="polite"
                                            >
                                                Showing 1 to 10 of 57 entries
                                            </div>
                                        </div>
                                        <div class="col-sm-12 col-md-7">
                                            <div
                                                class="dataTables_paginate paging_simple_numbers"
                                                id="example2_paginate"
                                            >
                                                <ul class="pagination">
                                                    <li
                                                        class="paginate_button page-item previous disabled"
                                                        id="example2_previous"
                                                    >
                                                        <a
                                                            href="#"
                                                            aria-controls="example2"
                                                            data-dt-idx="0"
                                                            tabindex="0"
                                                            class="page-link"
                                                            >Previous</a
                                                        >
                                                    </li>
                                                    <li
                                                        class="paginate_button page-item active"
                                                    >
                                                        <a
                                                            href="#"
                                                            aria-controls="example2"
                                                            data-dt-idx="1"
                                                            tabindex="0"
                                                            class="page-link"
                                                            >1</a
                                                        >
                                                    </li>
                                                    <li
                                                        class="paginate_button page-item"
                                                    >
                                                        <a
                                                            href="#"
                                                            aria-controls="example2"
                                                            data-dt-idx="2"
                                                            tabindex="0"
                                                            class="page-link"
                                                            >2</a
                                                        >
                                                    </li>
                                                    <li
                                                        class="paginate_button page-item"
                                                    >
                                                        <a
                                                            href="#"
                                                            aria-controls="example2"
                                                            data-dt-idx="3"
                                                            tabindex="0"
                                                            class="page-link"
                                                            >3</a
                                                        >
                                                    </li>
                                                    <li
                                                        class="paginate_button page-item"
                                                    >
                                                        <a
                                                            href="#"
                                                            aria-controls="example2"
                                                            data-dt-idx="4"
                                                            tabindex="0"
                                                            class="page-link"
                                                            >4</a
                                                        >
                                                    </li>
                                                    <li
                                                        class="paginate_button page-item"
                                                    >
                                                        <a
                                                            href="#"
                                                            aria-controls="example2"
                                                            data-dt-idx="5"
                                                            tabindex="0"
                                                            class="page-link"
                                                            >5</a
                                                        >
                                                    </li>
                                                    <li
                                                        class="paginate_button page-item"
                                                    >
                                                        <a
                                                            href="#"
                                                            aria-controls="example2"
                                                            data-dt-idx="6"
                                                            tabindex="0"
                                                            class="page-link"
                                                            >6</a
                                                        >
                                                    </li>
                                                    <li
                                                        class="paginate_button page-item next"
                                                        id="example2_next"
                                                    >
                                                        <a
                                                            href="#"
                                                            aria-controls="example2"
                                                            data-dt-idx="7"
                                                            tabindex="0"
                                                            class="page-link"
                                                            >Next</a
                                                        >
                                                    </li>
                                                </ul>
                                            </div>
                                        </div>
                                    </div>
                                </div>
                            </div>
                            <!-- /.card-body -->
                        </div>
              
</template>

<script>
export default {
    name: "List",
    mounted() {
        this.$store.dispatch("allAboutFromDatabase");
    },
    computed: {
        getAllAbout(){
            return this.$store.getters.getAboutFormGetters;
        }
     
    },
    methods:{
        deleteAbout(id){
            console.log("its ok")
            axios.delete(`/about/${id}`)
           .then(() => {
                    this.$store.dispatch("allAboutFromDatabase");
                    Toast.fire({
                        icon: "success",
                        type: "success",
                        title: "About Deleted successfully"
                    });
                })
                .catch(() => {
                    console.log("Error........");
                });
        }
    }
};
</script>
