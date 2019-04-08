# ci_rapi
CI Library for RAJA API Wilayah
read more --> [https://docs.rajaapi.com/dokumentasi/wilayah]

## How To Use
    public function test(){
        $this->load->library('ci_rapi');
        
        //check aktif
        $result = $this->ci_rapi->isActive();
        
        //get wilayah
        $data  = $this->ci_rapi->getProvinsi();
        $data1 = $this->ci_rapi->getKabupaten(33);
        $data2 = $this->ci_rapi->getKecamatan(3301);
        $data3 = $this->ci_rapi->getKelurahan(3301010);

        //custom set
        $this->ci_rapi->setUrl('wilayah/kabupaten');
        $this->ci_rapi->setArgs('idpropinsi', 33);
        $data4 = $this->ci_rapi->fetch();

        //show result
        echo '<pre>';
        var_dump($data4);
        echo '</pre>';
        die();
    }
