# QR Generator Laravel


follow this step 

install package

composer require simplesoftwareio/simple-qrcode


<h1>Register QR Code Service</h1> > config/app.php

'providers' => [
    ....                
    SimpleSoftwareIO\QrCode\QrCodeServiceProvider::class,
],

'aliases' => [
    ....                
    'QrCode' => SimpleSoftwareIO\QrCode\Facades\QrCode::class,
]

php artisan make:controller QrCodeController


public function index()
{
  return view('qrcode');
}

Route::get('/qrcode', [QrCodeController::class, 'index']);

<link href="https://cdn.jsdelivr.net/npm/bootstrap@5.0.2/dist/css/bootstrap.min.css" rel="stylesheet"/>

Simple QR Code

{!! QrCode::size(300)->generate('http://127.0.0.1:8000/qr-generate') !!}


Color QR Code

{!! QrCode::size(300)->backgroundColor(255,90,0)->generate('http://127.0.0.1:8000/qr-generate') !!}


