Português | [English](README.md)

# Relatório de manutenção de WordPress

> **Arquivado (2026-11).** Entrega pontual de maio de 2025. Não há código aqui, só o registro do serviço.

## O que foi

Uma manutenção (03/05/2025) no site WordPress de uma pequena empresa. O trabalho teve três partes:

- **Atualização do PHP.** PHP atualizado para a versão mais recente compatível com o tema e os plugins; `memory_limit`, `max_execution_time` e limites de upload ampliados no `php.ini` e no `.htaccess`; compatibilidade testada depois.
- **Desempenho.** CSS e JS minificados, cache de navegador e compressão gzip ligados no `.htaccess`, plugins e scripts sem uso removidos, imagens comprimidas.
- **Segurança.** Cabeçalhos de segurança (`X-Frame-Options`, `X-Content-Type-Options`, uma `Content-Security-Policy`), permissões mais restritas no `wp-config.php`, varredura de malware, todos os plugins e temas atualizados, execução de PHP bloqueada em `uploads/`, HTTPS e domínio principal forçados por redirecionamento.

Um backup completo (arquivos e banco) foi feito antes de qualquer mudança e um backup final foi entregue ao cliente.

## O que ficou de aprendizado

- **Backup antes de mexer em qualquer coisa.** É o que torna seguro fazer o resto num site no ar.
- **Aumentar limite não é conserto.** `memory_limit` e `max_execution_time` maiores escondem plugin lento. Tirar o que não era usado rendeu mais velocidade que os limites novos.
- **Cabeçalho envelhece.** O `X-XSS-Protection` estava no relatório original; navegador atual ignora, e a orientação hoje é uma boa `Content-Security-Policy`.
- **Relatório faz parte da entrega.** Anotar cada mudança deixou o serviço fácil de explicar ao cliente e fácil de desfazer.

## Licença

Todos os direitos reservados.
