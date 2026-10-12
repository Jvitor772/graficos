def calcular(a, op, b):
    if op == "+": return a + b
    if op == "-": return a - b
    if op == "*": return a * b
    if op == "/":
        if b == 0:
            print("Erro: divisão por zero!")
            return None
        return a / b
    print("Operador inválido!")
    return None

def main():
    print("=== CALCULADORA ===")
    print("Operadores: + - * /")
    print("Digite 'sair' para encerrar\n")

    while True:
        entrada = input("Cálculo: ").strip()
        if entrada.lower() == "sair":
            break

        try:
            for op in ["+", "-", "*", "/"]:
                if op in entrada:
                    partes = entrada.split(op, 1)
                    a = float(partes[0].strip())
                    b = float(partes[1].strip())
                    resultado = calcular(a, op, b)
                    if resultado is not None:
                        print(f"= {resultado}\n")
                    break
            else:
                print("Formato inválido. Ex: 10 + 5\n")
        except ValueError:
            print("Digite números válidos. Ex: 10 + 5\n")

if __name__ == "__main__":
    main()
