# install instructions

```
# remove executable bit, so the original files cannot be executed anymore -> so we don't have to delete them
for f in /etc/update-motd.d/* ; do
  echo "removing executable bit for ${f}"
  sudo chmod -x $f
done

# get this repo's MotD, make it executable, symlink in /etc/update-motd.d/
git clone https://github.com/Momro/motd "${HOME}"/motd && cd "${HOME}/motd" && sudo chmod +x 00-custom-header && sudo ln -s "${HOME}/motd/00-custom-header" /etc/update-motd.d/00-custom-header

