# Sistema de Verificação Modular de Segurança

🔍 **Descrição**  
Este programa verifica condições de segurança em operações modulares, calculando divisões modulares (`H⊘G mod n`) e exponenciações modulares (`a^x mod n1`), aplicando os **Teoremas de Fermat e Euler** para otimização.

## 📌 Funcionamento

### 1. Entradas
O programa solicita:
- **H, G, n**: Valores para calcular `a = H⊘G mod n` (divisão modular).
- **x, n1**: Expoente e módulo para calcular `a^x mod n1`.

### 2. Etapas do Cálculo
1. **Verifica se `G` e `n` são coprimos (MDC = 1)**  
   - Se não forem, a divisão modular é impossível (encerra com erro).
2. **Calcula o inverso modular de `G` em `ℤₙ`**  
   - Usa o **Algoritmo de Euclides Estendido**.
3. **Calcula a base `a = H * G⁻¹ mod n`**  
   - Representa a divisão modular `H⊘G`.
4. **Verifica se `a` e `n1` são coprimos**  
   - Se não forem, não é possível aplicar Fermat/Euler (encerra com erro).
5. **Aplica o Teorema de Fermat (se `n1` é primo) ou Euler (se `n1` é composto)**  
   - **Fermat**: `a^(n1-1) ≡ 1 mod n1` → reduz o expoente `x`.  
   - **Euler**: `a^φ(n1) ≡ 1 mod n1` → usa a função totiente `φ(n1)`.
6. **Decompõe o expoente `x` em `x = x1*q + r`**  
   - Simplifica `a^x mod n1` para `(1^q * a^r) mod n1`.
7. **Exibe o resultado final e uma verificação direta**  
   - Compara com o cálculo sem otimização para validar.

