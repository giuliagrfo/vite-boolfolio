<script>
export default {
    name: 'ContactsView'
}  
</script>

<template>
    <div class="container mt-5">
        <h1>Contacts</h1>
        <form action="">
            <div class="mb-3">
                <label for="" class="form-label">Name</label>
                <input type="text" name="" id="" class="form-control" placeholder="name"
                    aria-describedby="fullNameHelper">
                <small id="fullNameHelper" class="text-muted">Add your name</small>
            </div>
            <div class="mb-3">
                <label for="" class="form-label">Last Name</label>
                <input type="text" name="" id="" class="form-control" placeholder="last name"
                    aria-describedby="fullNameHelper">
                <small id="fullNameHelper" class="text-muted">Add your last name</small>
            </div>
            <div class="mb-3">
                <label for="" class="form-label">Email</label>
                <input type="email" name="" id="" class="form-control" placeholder="name@example.com"
                    aria-describedby="emailHelper">
                <small id="emailHelper" class="text-muted">Add your email address</small>
            </div>

            <div class="mb-3">
                <label for="" class="form-label">Message</label>
                <textarea class="form-control" name="" id="" rows="5"></textarea>
            </div>

            <button type="submit" class="btn btn-primary">Contact Me</button>
        </form>
    </div>

</template>

<style lang="scss" scoped>

</style>