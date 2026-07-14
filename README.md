# Lapka 36 RMK Firmware

## Как сделать локальный билд

1. Создаём директорию, например `lapka-rmk`

`mkdir lapka-rmk`

2. Клонируем этот репозиторий

`git clone https://github.com/braindefender/lapka-rmk-config`

3. Клонируем RMK

`git clone https://github.com/HaoboGu/rmk.git rmk`

4. Должна получиться такая структура:

```
lapka-rmk
|- lapka-rmk-config
|- rmk
```
5. Переходим в `rmk` и переключаемся на спец. коммит

```
cd rmk
git checkout d9067b567fd72d45c10b282989f2faea8321132c
```

6. Применяем патч:

`git apply ../lapka-rmk-config/patch/wellum.patch`

7. Переходим в `lapka-rmk-config` и делаем билд прошивки

```
cd ../lapka-rmk-config
cargo make uf2 --release
```

8. Полученные файлы находятся в папке `firmware`.

9. Прошиваем и пользуемся.

---

RMK is a feature-rich and easy-to-use keyboard firmware.

### Additional notes

RMK defaults to USB-priority mode if a USB cable is connected. After flashing, remember to disconnect the USB cable, or [switch to BLE-priority mode](https://rmk.rs/docs/features/wireless.html#multiple-profile-support) by pressing User11(Switch Output) key.
