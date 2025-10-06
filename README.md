# Pilha (Estrutura de Dados com Ponteiros)

---

## 🎯 Objetivos da Atividade

Ao concluir esta atividade, você deverá ser capaz de:

* Compreender o conceito de **pilha** como uma **estrutura de dados linear**.
* Entender o princípio **LIFO (Last In, First Out)** — o último elemento a entrar é o primeiro a sair.
* Implementar uma pilha **dinâmica** utilizando **ponteiros** em C++.
* Utilizar **alocação dinâmica de memória** (`malloc` e `free`) para manipular elementos.

---

## 🧩 Conceito de Pilha

Uma **pilha** é uma estrutura onde o **último elemento inserido é o primeiro a ser removido**.

💡 **Analogia**: imagine uma pilha de pratos em uma cozinha — você sempre coloca um novo prato no topo e, quando precisa de um, retira o prato que está por cima.

### Estrutura LIFO

* **L**ast **I**n → o último elemento inserido...
* **F**irst **O**ut → ...é o primeiro a ser removido.

---

## 🧠 Representação na Memória

Cada elemento da pilha é representado por um **nó** que contém:

* Um **valor** (dado armazenado);
* Um **ponteiro** para o **próximo nó** da pilha.

O ponteiro **`topo`** sempre aponta para o último elemento inserido.

```
Topo → [valor | prox] → [valor | prox] → NULL
```

---

## 🧱 Estrutura Base do Código

O código fornecido define a estrutura `NO` e um ponteiro global `topo`:

```cpp
struct NO {
    int valor;
    NO* prox;
};

NO* topo = NULL;
```

O programa já possui um menu com as opções principais:

1. Inicializar pilha
2. Inserir elemento (Push)
3. Remover elemento (Pop)
4. Sair

---

## 🧮 Atividade Proposta

Faça um **fork** deste repositório e implemente as seguintes funções no arquivo `Pilha.cpp`.

---

### ✅ 1. Função `push()`

Responsável por **inserir um novo elemento** no topo da pilha.

**Etapas sugeridas:**

1. Alocar memória dinamicamente para um novo nó (`malloc` ou `new`);
2. Ler o valor digitado pelo usuário e armazenar em `novo->valor`;
3. Fazer o novo nó apontar para o antigo topo (`novo->prox = topo`);
4. Atualizar o ponteiro `topo` para apontar para o novo nó;
5. Exibir uma mensagem de confirmação.

**Exemplo de execução:**

```
Digite o elemento: 10
Elemento 10 inserido no topo da pilha.
```

---

### ✅ 2. Função `pop()`

Responsável por **remover o elemento que está no topo** da pilha.

**Etapas sugeridas:**

1. Verificar se a pilha está vazia (`topo == NULL`);

   * Se estiver, exibir `"Pilha vazia!"` e retornar.
2. Criar um ponteiro auxiliar (`NO* aux = topo`);
3. Exibir o valor removido (`aux->valor`);
4. Atualizar `topo` para o próximo elemento (`topo = topo->prox`);
5. Liberar a memória do nó removido (`free(aux)`).

**Exemplo de execução:**

```
Elemento removido: 10
```

---

### ✅ 3. Função `inicializar()`

Já está parcialmente implementada.
Ela deve **liberar todos os nós existentes**, garantindo que não haja vazamento de memória.

**Fluxo da função:**

* Percorrer toda a pilha liberando os nós com `free()`;
* Definir `topo = NULL`.

---

### 🔍 Dica de Implementação Visual

**Antes de inserir elementos:**

```
topo → NULL
```

**Após inserir 3 elementos (10, 20, 30):**

```
topo → [30] → [20] → [10] → NULL
```

**Após remover um elemento:**

```
topo → [20] → [10] → NULL
```

---

## 🧪 Testes sugeridos

Execute as operações na seguinte ordem para testar sua implementação:

1. Inicialize a pilha
2. Insira 3 elementos (`10`, `20`, `30`)
3. Remova 1 elemento (esperado: remove `30`)
4. Insira outro elemento (`40`)
5. Remova todos os elementos até a pilha ficar vazia
6. Tente remover novamente (esperado: mensagem “Pilha vazia”)

---

## 🧭 Desafio Extra

Implemente uma função `exibir()` que percorra a pilha do topo até o fim, mostrando todos os elementos.

**Exemplo:**

```
Conteúdo da pilha:
40 → 20 → 10
```

---

## 💾 Entrega

* Faça o **fork** do repositório.
* Implemente as funções `push()` e `pop()` conforme descrito.
* Realize **commits** explicativos (por exemplo: “Implementação da função push()”).
* Envie o link do repositório no **Teams** 

---

Quer que eu também adicione a versão completa corrigida e comentada do arquivo `Pilha.cpp` (com `push()` e `pop()` implementados e explicações linha a linha)? Isso ajudaria os alunos a entender a lógica internamente.
