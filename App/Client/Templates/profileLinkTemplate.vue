<template>
    <div>
        <!-- logged in dropdown -->
        <ul class="nav navbar-nav navbar-right" v-if='this.$store.state.user.username'>
            <li>
                <p class="navbar-text">Welcome, {{this.$store.state.user.username}}!</p>
            </li>
            <li class="dropdown">
                <a href="#" class="dropdown-toggle " data-toggle="dropdown"><b>Profile Options</b> <span class="caret"></span></a>
                <ul id="login-dp" class="dropdown-menu logout-profile">
                    <li>
                        <button v-on:click.prevent="goToEvents" type="submit" class="btn btn-primary btn-block">Events</button>
                    </li>
                    <li>
                        <button v-on:click.prevent="goToMatches" type="submit" class="btn btn-primary btn-block">My Matches</button>
                    </li>
                    <li>
                        <button v-on:click.prevent="goToMyProfile" type="submit" class="btn btn-primary btn-block">My Room</button>
                    </li>
                    <li>
                        <button v-on:click.prevent="editProfile" type="submit" class="btn btn-primary btn-block">Update Profile</button>
                    </li>
                    <li>
                        <button v-on:click.prevent="goToProfile" type="submit" class="btn btn-primary btn-block">Profile</button>
                    </li>
                    <li>
                        <button type="submit" class="btn btn-primary btn-block" v-on:click.prevent="logout">Logout</button>
                    </li>
            </li>
        </ul>
        <!-- default dropdown -->
        <ul class="nav navbar-nav navbar-right" v-else>
            <li>
                <p class="navbar-text">Already have an account?</p>
            </li>
            <li class="dropdown">
                <a href="#" class="dropdown-toggle" data-toggle="dropdown"><b>Login</b> <span class="caret"></span></a>
                <ul id="login-dp" class="dropdown-menu">
                    <li>
                        <div class="row">
                            <div class="col-md-12">
                                Sign in with
                                <div class="social-buttons">
                                    <a href="/auth/facebook" class="btn btn-fb"><i class="fa fa-facebook"></i> Facebook</a>
                                    <a href="/auth/twitter" class="btn btn-tw"><i class="fa fa-twitter"></i> Twitter</a>
                                </div>
                                or
                                <form class="form" role="form" method="post" action="login" accept-charset="UTF-8" id="login-nav">
                                    <login></login>
                                    <div class="checkbox">
                                        <label>
                                            <input type="checkbox"> Stay logged in
                                        </label>
                                    </div>
                                </form>
                            </div>
<!--                             <div class="bottom text-center">
                                Need an account?
                                <router-link to='/signup'><a href="#/signup"><b>Sign up</b></a>
                                </router-link>
                            </div> -->
                        </div>
                    </li>
                </ul>
            </li>
        </ul>
    </div>
</template>