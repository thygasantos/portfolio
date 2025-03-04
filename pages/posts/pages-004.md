---

title: ENCRYPTION BCRYPT TYPE HASH

date: 2023/3/12

description: Learn more about ENCRYPTION BCRYPT TYPE HASH.

tag: news

author: You

---


bcrypt é um método de criptografia do tipo hash para senhas baseado no Blowfish. Foi criado por Niels Provos e David Mazières e apresentado na conferência da USENIX em 1999 [1].

Este método apresenta uma segurança maior em relação à maioria dos outros métodos criptográficos que é a implementação da variável "custo" que é proporcional à quantidade de processamento necessária para criptografar a senha. O método é conhecido como hash adaptativo às melhorias futuras de hardware por ter esta característica, pois pode permanecer resistente à ataques do tipo "força-bruta" com o tempo usando custos maiores de processamento.

Ao contrário do método tradicional "crypt" (concebido em 1976), o algoritmo bcrypt não possui as restrições da época que eram pouco processamento e poucos espaço (bytes) para guardar o salt e o hash gerado da senha criptografada [2].

O algoritmo bcrypt foi implementado em diversas linguagens como Python, Perl, Ruby, Java, C# e outras [3], além de possuir implementação também para a função "crypt" do UNIX. 
