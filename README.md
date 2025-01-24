# Русскоговорящее сообщество Meshtastic - RUMesh

Вы находитесь в репозитории портала [Meshtastic русскоговорящее сообщество](https://rumesh.timurey.ru/)

Сейчас портал находится в пре-альфа версии и очень нуждается в помощи сообщества.

Необходимо написать/перевести/скопировать материал для наполнения.

За основу портала взяты исходные коды аналогичного китайского сообщества [meshcn.net](https://meshcn.net/)

Что Мы можем сделать:

- обсудить потребность в необходимой информации, составить контент-план
- перевести имеющуюся статью с китайского языка на великий могучий
- перевести любой материал с любого другого языка
- написать собственную статью
- внести исправление, дополнение в имеющуюся статью
- внести изменения в верстку
- нарисовать логотип/favicon для портала
- перенести исходный код из личного репозитория в репозиторий организации
- предложить более удобное доменное имя
- предложить любую идею, улучшение для портала
- поработать над имеющимися задачами в issues

## Как работает портал?

Материал для сайта (статьи, страницы )хранятся в виде ```markdown``` файлов. [Подробнее](https://www.markdownguide.org) о формате.

Портал представляет собой статический веб-сайт, который генерируется движком [hexo.io](https://hexo.io/ru/) из упомянутых выше ```markdown``` файлов.

Хостинг осуществляется на сервере [github pages](https://pages.github.com), сборка сайта производится автоматически при внесении изменений в основную ветку ```main```

На данный момент стати раскладываются по категориям ```categories/Учебник/``` и ```categories/Новости/```

В статьях есть тэги, которые помогают найти

## Я хочу написать или перевести статью, я знаю, что такое git, nodejs?

- **fork**: сделайте fork репозитория, клонируйте репозиторий на локальный компьютер, сделайте необходиме изменения
- **debug**: проверьте правильность работы портала локально (смотри ниже)
- **PR**: сделайте pull-request ваших изменений
- Вы великолепны!

При переводе статей с других языков обязательно проверяйте, под какой лицензией выложена исходная статья. Старайтесь указывать оригинального автора, даже если это не предусмотрено исходной лицензией.

Ваш вклад поможет порталу развиваться и способствовать развитию Meshtastic сети.

## Я хочу написать или перевести статью, но я НЕ умею и НЕ хочу научиться в git?

- Готовь материал на русском языке, высылай его в группу админ состава портала в [telegram](https://t.me/+R0bpGAZ-fzZmZmRi)
- Вы великолепны!

Ваш вклад поможет порталу развиваться и способствовать развитию Meshtastic сети.

## Как запустить портал локально на своем компьютере?

```bash
npm install -g hexo-cli
git clone https://github.com/timurey/timurey.github.io
cd ./timurey.github.io
npm install
hexo server
```

## Формат фалов статей и страниц
Документация к движку ```hexo.io``` почти полностью переведена на русский язык [https://hexo.io/ru/docs/](https://hexo.io/ru/docs/)

В дополнение к основным тегам шапки статьи ([https://hexo.io/ru/docs/front-matter](https://hexo.io/ru/docs/front-matter)) были добавлены параметры, определяющие автора материала. Например:

```yaml
author:
  name: timurey
  url: https://t.me/timurey
  source:
    url: https://meshcn.net/introduction/
    author: Hays Chan | 陈希
```

здесь:
- ```name``` - имя автора на портале, отображается внизу статьи (по умолчанию ```admin```)
- ```url``` - ссылка на профиль автора или его социальную сеть (пока не отображается)
- ```source``` - признак, что статья была переведена с другого источника
- ```source.url``` - ссылка на статью-первоисточник
- ```source.author``` - автор статьи-первоисточника

для образца можно брать [introduction.md](source/_posts/introduction.md)

[🔗 группа Meshtastic Russia в telegram](https://t.me/meshtastic_russia)
[🔗 группа админ состава портала в telegram](https://t.me/+R0bpGAZ-fzZmZmRi)
