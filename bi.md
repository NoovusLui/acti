# doks

 zhaleff 

```bash
cp home/arq/^config.zsh destino/
```
^config.zsh = tudo exceto config.zsh


```bash
cp home/arq/^(config.zsh|theme.rasi) destino/
```
Aqui ele copia tudo menos config.zsh e theme.rasi

```bash
cp home/arq/^config.zsh(.) destino/
```
(.) = apenas arquivos normais, Só arquivos (ignorar diretórios)

---
copy_except() {
  local src="$1"
  local dest="$2"
  shift 2
  local exclude_pattern="^(${(j:|:)@})"
  cp -r "$src"/$~exclude_pattern "$dest"
}

uso:
copy_except home/arq destino config.zsh
ou multiplos:
copy_except home/arq destino config.zsh theme.rasi
alias cx='copy_except'
