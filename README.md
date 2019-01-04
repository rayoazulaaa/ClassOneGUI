    // Variables declaration - do not modify                     
    private javax.swing.JButton btnMas1;
    private javax.swing.JButton btnMas2;
    private javax.swing.JButton btnMas3;
    private javax.swing.JButton btnResult;
    private javax.swing.JButton btnTwoDigs;
    private javax.swing.JComboBox<String> cmbDig2;
    private javax.swing.JComboBox<String> cmbDig3;
    private javax.swing.JComboBox<String> cmbDigitos;
    private javax.swing.JComboBox<String> cmbSim2;
    private javax.swing.JComboBox<String> cmbSimbolos;
    private javax.swing.JScrollPane jScrollPane1;
    private javax.swing.JLabel lblDescripcion;
    private javax.swing.JLabel lblDig1;
    private javax.swing.JLabel lblDig2;
    private javax.swing.JLabel lblDig3;
    private javax.swing.JLabel lblEjercicio1;
    private javax.swing.JLabel lblResultados;
    private javax.swing.JLabel lblSim2;
    private javax.swing.JLabel lblSimbolos;
    private javax.swing.JLabel lblStep2;
    private javax.swing.JLabel lblStepOne;
    private javax.swing.JList<String> lstOperaciones;
    ////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////
    private void btnMas1ActionPerformed(java.awt.event.ActionEvent evt) {                                        
        this.cmbDigitos.setSelectedItem("4");
        this.cmbSimbolos.setSelectedItem("+");
        this.cmbSimbolos.setEnabled(false);
        this.cmbDig2.setSelectedItem("5");
        this.cmbSim2.setSelectedItem("=");
        this.cmbSim2.setEnabled(false);
        this.cmbDig3.setSelectedItem("?");
        this.cmbDig3.setEnabled(false);
        this.btnMas1.setEnabled(false);
        this.cmbDig2.setEnabled(false);
        this.cmbDigitos.setEnabled(false);
        this.btnTwoDigs.setEnabled(true);
        this.btnResult.setEnabled(false);
        this.status++;
    }   
    ///////////////////////////////////////////////////////////////////////////////////////////////////////////////////////
    private void btnTwoDigsActionPerformed(java.awt.event.ActionEvent evt) {                                           
        int numero_1 = Integer.parseInt(this.cmbDigitos.getSelectedItem().toString());
        int numero_2 = Integer.parseInt(this.cmbDig2.getSelectedItem().toString());
        this.lblResultados.setText(Integer.toString(numero_1 + numero_2));
        this.btnResult.setEnabled(true);
        JOptionPane.showMessageDialog(null, this.status);
        switch(status){
            case 1 : this.btnResult.setEnabled(false);this.btnMas1.setEnabled(false);this.btnMas2.setEnabled(true);break;
            case 2 :  this.btnResult.setEnabled(false);this.btnMas1.setEnabled(false);this.btnMas2.setEnabled(false);this.btnMas3.setEnabled(true);break;
            case 3 : this.btnMas3.setEnabled(false);this.btnTwoDigs.setEnabled(false);this.btnResult.setEnabled(true);break;
            case 4 : this.status = 0; JOptionPane.showMessageDialog(null, "Se Reinicio el contador");break;
        }
        this.btnTwoDigs.setEnabled(false);
    }  
    ///////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////
   private void btnMas2ActionPerformed(java.awt.event.ActionEvent evt) {                                        
        this.cmbDigitos.setSelectedItem("1");
        this.btnMas2.setEnabled(false);
        this.cmbSimbolos.setSelectedItem("+");
        this.cmbDig2.setSelectedItem("3");
        this.cmbSim2.setSelectedItem("=");
        this.cmbDig3.setSelectedItem("?");
        this.btnTwoDigs.setEnabled(true);
        this.btnResult.setEnabled(false);
        this.status++;
    } 
    ////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////
    private void btnMas3ActionPerformed(java.awt.event.ActionEvent evt) {                                        
        this.cmbDigitos.setSelectedItem("1");
        this.cmbSimbolos.setSelectedItem("+");
        this.cmbDig2.setSelectedItem("3");
        this.cmbSim2.setSelectedItem("+");
        this.cmbDig3.setSelectedItem("5");
        this.btnMas3.setEnabled(false);
        this.btnTwoDigs.setEnabled(true);
        this.btnResult.setEnabled(false);
        this.status++;
    }     
    ////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////
    private void btnResultActionPerformed(java.awt.event.ActionEvent evt) {                                          
        int numero_1,numero_2,numero_3 = 0;
        this.cmbSim2.setSelectedItem("+");
        this.cmbDig3.setSelectedItem("5");
        this.cmbDig2.setSelectedItem("3");
        this.cmbDigitos.setSelectedItem("1");
        if(this.status == 0){
            numero_1 = Integer.parseInt(this.cmbDigitos.getSelectedItem().toString());
            numero_2 = Integer.parseInt(this.cmbDig2.getSelectedItem().toString());
            numero_3 = Integer.parseInt(this.cmbDig3.getSelectedItem().toString());
            this.lblResultados.setText(Integer.toString(numero_1 + numero_2 + numero_3));
        }else{
            numero_1 = Integer.parseInt(this.cmbDigitos.getSelectedItem().toString());
            numero_2 = Integer.parseInt(this.cmbDig2.getSelectedItem().toString());
            if(this.cmbDig3.getSelectedItem().toString().equals("?")){
                numero_3 = 5;
            }else{
                numero_3 = Integer.parseInt(this.cmbDig3.getSelectedItem().toString());
            }
        }
        this.lblResultados.setText(Integer.toString(numero_1 + numero_2 + numero_3));
        JOptionPane.showMessageDialog(null, "sigue dando click a los botones");
        this.btnMas1.setEnabled(true); 
        this.btnResult.setEnabled(false);
    }  
