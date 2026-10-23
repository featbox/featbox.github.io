<p align="center"><img src="assets/marcas/featbox-t3-favicon.svg" width="96" alt="Featbox"></p>

# Featbox™

**Trabalhar com IA sem perder o controle.**

Esta é a página pública do Featbox. Os apps são de código fechado; a página e a documentação de apresentação são abertas.

## Em uma frase (para todo mundo)
Você pede uma coisa para a IA, ela faz outra, e uma semana depois ninguém lembra por que o projeto ficou assim. O Featbox é um pacote de três apps para Windows que guarda suas notas e seus documentos no seu computador e registra cada decisão: a IA pede, você aprova ou recusa, e fica anotado para sempre.

| App | Para que serve | Plano |
|---|---|---|
| **FeatReader** | ler documentos (md, txt, pdf, docx) com destaques, notas, áudio e leitura em voz | grátis |
| **FeatDesk** | escrever e organizar notas numa pasta sua | pacote pago |
| **FeatRoom** | registrar decisões e conferir que o histórico não foi mexido | pacote pago |

No piloto, tudo fica liberado.

## Por dentro (para quem é técnico)
- **Stack:** Electron, um processo por app, instalação por usuário sem administrador. contextIsolation ligado, nodeIntegration desligado, sandbox ligado, CSP `default-src 'none'`; a interface só fala com o disco por IPC validado.
- **Local primeiro:** nenhuma função usa IA de nuvem na 0.5.0. O FeatDesk bloqueia http(s) e ws na sessão. O modelo de linguagem do FeatRoom é opcional e só aceita servidor em localhost (compatível com a API da OpenAI).
- **Registro encadeado:** `eventos.jsonl` só acrescenta; cada evento guarda o SHA-256 do anterior e o app verifica a cadeia inteira. Uma cadeia pessoal e uma por projeto, dentro da pasta do projeto.
- **Várias IAs, um contexto:** o registro é texto aberto na pasta do projeto, então qualquer assistente que trabalhe ali lê o mesmo contexto e registra no mesmo formato. Nenhum provedor recebe o projeto inteiro.
- **Aprovação de regras, não de cada ação:** a IA registra um pedido; só a aprovação humana transforma o pedido em regra. Recusas ficam registradas.
- **Fichas de módulo:** uma ficha curta por módulo, ligada a um commit; se entra código depois dela, o selo vira "desatualizada".
- **Testes:** 42 (FeatDesk), 48 (FeatReader), 4 da cadeia (FeatRoom) e teste de fumaça de cada app instalado.

## Estado
Versão **0.5.0** para Windows 10 e 11, em avaliação. Memória local e "Perguntar ao projeto" em desenvolvimento. Preço e licença definitiva depois do piloto.

## Piloto
Procuro 5 pessoas que toquem um projeto longo com IA, para usar por 2 semanas. Inscrição: [featbox.company@gmail.com](mailto:featbox.company@gmail.com?subject=Quero%20participar%20do%20piloto%20Featbox).

## Quem constrói
Renato Manduca, Garopaba (SC). Mais de uma década em operação de restaurante antes do software. Construo com IA e com uma pessoa aprovando o que importa.

---
© 2026 Renato Manduca. Featbox™ e os nomes FeatDesk, FeatReader e FeatRoom são marcas de uso do autor. Fontes IBM Plex e Literata sob a licença OFL (ver `assets/fonts`).
