<template>
    <div class="container my-5">
        <h1 class="text-center text-dark mb-5">Create QR Code in 3 Steps</h1>
        <div class="row">
            <div class="col-md-4 text-center">
                <div class="card h-100">
                    <div class="card-body">
                        <h5 class="card-title">Step 1</h5>
                        <p class="card-text">Choose The Type</p>
                        <img src="/img/file.png" alt="QR Code" class="img-fluid mb-3" />
                    </div>
                </div>
            </div>
            <div class="col-md-4 text-center">
                <div class="card h-100">
                    <div class="card-body">
                        <h5 class="card-title">Step 2</h5>
                        <p class="card-text">Generate QR Code</p>
                        <img src="/img/website.png" alt="QR Code" class="img-fluid mb-3" />
                        <button type="button" class="btn btn-primary">GENERATE</button>
                    </div>
                </div>
            </div>
            <div class="col-md-4 text-center">
                <div class="card h-100">
                    <div class="card-body">
                        <h5 class="card-title">Step 3</h5>
                        <p class="card-text">Customize & Download</p> 
                            <img src="/img/qr.png" alt="QR Code" class="img-fluid mb-3" />  
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'QRCodeGenerator'
}
</script>