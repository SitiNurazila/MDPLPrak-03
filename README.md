# MDPLPrak-03


        public void Depresiasi () {

                double BPAset;
                double NilaiResidu;
                double EstimasiUmur;
                double AwalDepresiasi;
                double AkhirDepresiasi;

                BPAset = Double.parseDouble(txtBPAset.getText());
                NilaiResidu = Double.parseDouble(txtNilaiResidu.getText());
                EstimasiUmur = Double.parseDouble(txtEstimasiUmur.getText());
                AwalDepresiasi = Double.parseDouble(txtAwalDepresiasi.getText());
                AkhirDepresiasi= Double.parseDouble(txtAkhirDepresiasi.getText());

                if (BPAset!=0 && NilaiResidu!=0 && EstimasiUmur!=0 && AwalDepresiasi!=0 && AkhirDepresiasi!=0){
                    if (AwalDepresiasi<AkhirDepresiasi){
                        taHasil.append("\"ASET           TH  AKUMULASI      SISA\"");
                        double depr = (BPAset-NilaiResidu)/EstimasiUmur;
                        double x;
                        for( x = AwalDepresiasi; x<=AkhirDepresiasi; x++){
                            double akumulasi = x * depr;
                            double sisa = BPAset - akumulasi;
                            int masa = (int) x;
                            String result = String.format("\n%.2f  %d   %.2f   %.2f", BPAset, masa, akumulasi, sisa);
                            taHasil.append(result);
                        }
                    }else{
                        taHasil.append("FALSE");
                    }
                }else{
                    taHasil.append("STOP");
                }
            }


            private void jButton1MouseClicked(java.awt.event.MouseEvent evt) {                                      
                // TODO add your handling code here:
                this.Depresiasi();
            }  
