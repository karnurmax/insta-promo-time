<template>
    <div class="container">
        <div class="row justify-content-center">
            <div class="col-md-8">
                <div class="card">
                    <div class="card-header">App component</div>

                    <div class="card-body">
                        I'm an example component.
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    created() {
        const self = this;
        window.fbAsyncInit = function() {
            window.FB.init({
                appId: "578755332669760",
                cookie: true,
                xfbml: true,
                version: "5.0"
            });

            window.FB.AppEvents.logPageView();
        };

        (function(d, s, id) {
            var js,
                fjs = d.getElementsByTagName(s)[0];
            if (d.getElementById(id)) {
                return;
            }
            js = d.createElement(s);
            js.id = id;
            js.src = "https://connect.facebook.net/en_US/sdk.js";
            fjs.parentNode.insertBefore(js, fjs);
            window.FB.getLoginStatus(function(response) {
                self.statusChangeCallback(response);
            });
        })(document, "script", "facebook-jssdk");
    },
    mounted() {
        console.log("Component mounted.");
    },
    methods: {
        statusChangeCallback(response) {
            window.console.log("res", response);
        }
    }
};
</script>
