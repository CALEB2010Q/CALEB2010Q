Private Sub Button1_Click(sender As Object, e As EventArgs) Handles Button1.Click
    ' Validar que el sueldo sea un número
    If Not IsNumeric(TextBox1.Text) Then
        MsgBox("Solo se pueden ingresar números en el sueldo.")
        Exit Sub
    End If

    ' Calcular el IGSS
    Dim igss As Double
    If CheckBox1.Checked Then
        igss = Val(TextBox1.Text) * 0.0483
    Else
        igss = 0
    End If
    TextBox2.Text = igss.ToString("N2")

    ' Calcular el ISR
    Dim isr As Double
    If CheckBox2.Checked Then
        isr = Val(TextBox1.Text) * 0.05
    Else
        isr = 0
    End If
    TextBox3.Text = isr.ToString("N2")

    ' Calcular viáticos
    Dim viaticos As Double
    If CheckBox3.Checked Then
        viaticos = Val(TextBox1.Text) * 0.015
    Else
        viaticos = 0
    End If
    TextBox4.Text = viaticos.ToString("N2")

    ' Calcular comisiones
    Dim comisiones As Double
    If CheckBox4.Checked Then
        comisiones = Val(TextBox1.Text) * 0.01
    Else
        comisiones = 0
    End If
    TextBox5.Text = comisiones.ToString("N2")

    ' Calcular bono
    Dim bono As Double
    bono = 250
    TextBox6.Text = bono.ToString("N2")
End Sub
