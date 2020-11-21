Para simular a operação de um tanque onde a interação entre os componentes da adsorção são descritos pelas isoterma de Langmuir e por cinética de pseudo segunda ordem, o código abaixo pode ser observado como exemplo:

	langmuir_isoterm_dict = {'qml': 7.7, 'Kl': 0.79} 
	second_order_kinetics_dic = {'k': 0.023}

	tank = Tank(Isoterm.langmuir, langmuir_isoterm_dict, Kinetics.second_order, second_order_kinetics_dic)

	t, concentration = tank.run(concentration=1, mass_adsorption=2, volume=1,time=60)

	recovery = 1 - concentration[-1]/concentration[0]

Outras isotermas são definidas pela classe “Isoterm” e outras cinéticas por “Kinetics”. Isotermas e cinéticas não definidas nestas classes podem ser implementadas seguindo o padrão de construção destas classes.
