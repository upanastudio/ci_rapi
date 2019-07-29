# ci_rapi

CI Library for RAJA API Wilayah.
[read more here](https://docs.rajaapi.com/dokumentasi/wilayah)

## Installation

- Fork this Repo/Download this repo
- move `ci_rapi.php` to application/libraries folder on you Codeigniter projects.
- Voilla!.

## How To Use

```php
    public function test(){
        $this->load->library('ci_rapi');

        //check aktif
        $result = $this->ci_rapi->isActive();

        if(!$result){
            echo 'Raja Api Tidak Berfungsi!';
            return FALSE;
        }
        else{
            //get wilayah
            $data  = $this->ci_rapi->getProvinsi();
            $data1 = $this->ci_rapi->getKabupaten(33);
            $data2 = $this->ci_rapi->getKecamatan(3301);
            $data3 = $this->ci_rapi->getKelurahan(3301010);

            //custom set
            $this->ci_rapi->setUrl('wilayah/kabupaten');
            $this->ci_rapi->setArgs('idpropinsi', 33);
            $data_api = $this->ci_rapi->fetch();

            //show result
            echo '<pre>';
            print_r($data_api);
            echo '</pre>';
        }
        die();
    }
```

## Best Experience

You can combine this library with [select2chain](https://github.com/arhen/Select2Chain)
![ci_rapi + Select2Chain](https://s3.gifyu.com/images/ci_rapi2.gif)
