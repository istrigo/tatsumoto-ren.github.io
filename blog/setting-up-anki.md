# Setting up Anki

<img alt="anki" src="img/anki_logo.webp" style="float:right; max-height: 200px;">

[Anki](https://wiki.archlinux.org/index.php/Anki)
is a
[Spaced repetition](https://en.wikipedia.org/wiki/Spaced_repetition)
system (SRS), a program which allows you to create, manage and review
[flashcards](https://en.wikipedia.org/wiki/Flashcard).

There are currently many different SRS’s available.
[Mnemosyne](https://wiki.archlinux.org/index.php/Mnemosyne)
is considered to be a good Anki alternative.
However, I recommend that you stick with Anki.
It’s cross-platform, rich with features,
and supports [addons](https://ankiweb.net/shared/addons/), written in python.
There are many add-ons available that greatly aid language study, including a few of my own.
Because of the add-ons it's in my opinion really the only SRS application worth taking seriously.

What's most important, Anki is
[libre software](https://www.gnu.org/philosophy/free-sw.html)
that respects the users'
[freedom](https://web.archive.org/web/https://wiki.installgentoo.com/wiki/Freedom)
and community.
Unlike Supermemo, for example. But you can't use that on GNU/Linux and Android anyway.

Many language learners find Anki useful to quickly memorize (frontload)
core vocabulary of their target language (TL),
as well as boost their learning in the later stages.

It should be noted, however, that memorization of most vocabulary throughout all your language
learning phases should be done by
[studying sentences](https://web.archive.org/web/20210908131624/https://refold.la/roadmap/stage-2/a/basic-sentence-mining/#Mine-Sentences-Not-Words).
You will be making vocabulary cards in the process as well,
but much less so, and mostly for nouns.

The only downside of Anki is that it can be *a little bit* difficult to learn how to use.
Depending on how you use it you can either greatly decrease your
time spent studying or make using Anki a living hell for yourself.
If you find yourself confused about how Anki works,
it is recommended that you read the [Anki manual](https://docs.ankiweb.net/).
However, because it's highly detailed and technical,
the bulk of this article will focus on explaining the most useful Anki settings
to help you get things up and running as quickly as possible.

****

## Installation

There are two main ways to install Anki.

* Using your distribution's package manager ([pacman](https://wiki.archlinux.org/title/Pacman), apt, dnf, etc.).
* Using [pip](https://pip.pypa.io/en/stable/), a software installer for Python programs.

The first method guarantees that you'll have the right dependencies installed,
but you may get an old version of Anki.
Distro maintainers are not very good at keeping Anki up-to-date.
The second method guarantees that you get the latest version,
but you need to make sure you have all the dependencies installed.

Please don't install Anki via **FlatPak**, Snap packages or other non-native package managers.
People have been reporting various problems connected to these installation methods.

If you are running Wayland, please revert to [Xorg](https://wiki.archlinux.org/title/xorg)
to avoid possible issues.

### Using your package manager

* On Arch Linux
the official binary from
[GitHub](https://github.com/ankitects/anki/releases/)
can be obtained by installing
[anki-official-binary-bundle](https://aur.archlinux.org/packages/anki-official-binary-bundle/).
* If you're not an Arch Linux user,
I'm sure you'll find Anki in repositories of your distribution as well.
* Debian users and users of other *stable* distros should note that
outdated versions of Anki work poorly with most add-ons, especially new ones.
Use a version released at least 6 months ago or newer.

### Using pip

The latest version can be installed with the [aqt](https://pypi.org/project/aqt/) package.

```
$ pip install --upgrade aqt
```

* `pip` places executable files in `~/.local/bin/` by default.
Don't forget to add this directory to the
[PATH](faq.html#how-do-i-add-a-directory-to-the-path).
* To run Anki, type `anki` in the terminal and press Enter.
However, having a
[desktop entry](https://wiki.archlinux.org/title/Desktop_entries)
is more convenient.
Download
[this file](https://github.com/tatsumoto-ren/dotfiles/blob/main/.local/share/applications/anki.desktop)
and save it in `~/.local/share/applications`.
* If after installing Anki with `pip`
[Fcitx](https://wiki.archlinux.org/title/Fcitx)
doesn't work,
open your `~/.profile` (`~/.pam_environment` or a similar file)
and add `export QT_PLUGIN_PATH=/usr/lib/qt/plugins`.
* Anki depends on [mpv](https://mpv.io/) to play audio.
You have to install it separately.
* You may have to install [PyQt5](https://pypi.org/project/PyQt5/) as well.
* Anki `2.1.50` and later additionally requires
installing
[PyQtWebEngine](https://pypi.org/project/PyQtWebEngine/)
and
[PyQt5-stubs](https://pypi.org/project/PyQt5-stubs/)
from PyPI.
* `PyQt5` and `PyQtWebEngine` can be also obtained from the official Arch Linux repositories.

### Troubleshooting

If you're still unable to install or run Anki, refer to
[Anki Manual](https://docs.ankiweb.net/platform/linux/installing.html)
and
[Anki Betas guide](https://betas.ankiweb.net/).

## Sync your mobile device

By [signing up](https://ankiweb.net/account/register) for AnkiWeb
you can keep your cards synchronized across multiple machines.
You can also sync between devices.
Install [AnkiDroid](https://f-droid.org/en/packages/com.ichi2.anki/)
on your Android device and sync your collection.
This will allow you to review your flashcards when you're outside
and don't have access to your computer.
I prefer downloading the latest alpha from
[GitHub](https://github.com/ankidroid/Anki-Android/releases)
because AnkiDroid's releases are slow.

To sync your collection on desktop, press `Y` or click "Sync" on the toolbar.

I must warn you in advance though.
Don't sync your collection with AnkiWeb
if you are a heavy user of [subs2srs](https://aur.archlinux.org/packages/subs2srs/).
`subs2srs` decks take a lot of disk space. Use a different Anki profile to store them.

To make multiple profiles, press `File > Switch profile`.

## Import an example mining deck

After you install Anki, you need to set up a `Note Type`
to keep your flashcards formatted as you like.
Anki comes with a few basic Note Types but they aren't suited for learning Japanese.

Because making your own `Note Type` is a tedious process
consisting of essentially adding the fields you need and copy-pasting html and css,
I recommend you to import a pre-made mining deck.

A sample mining deck can be found here:
* AnkiWeb: https://ankiweb.net/shared/info/1557722832
* Mirror: https://t.me/ajatt_tools/16

## Japanese language support

Press "Tools" > "Add-ons" > "Get Add-ons" to download and install the
[AJT Furigana](https://ankiweb.net/shared/info/1344485230)
add-on.
Then restart.
The add-on is bundled with
[mecab](https://aur.archlinux.org/packages/mecab),
so you don't need to install any additional dependencies.

## Anki settings

I recommend the following settings.

### Preferences

You can access preferences by going to `Tools > Preferences…` on Anki’s main window.

* **Learn ahead limit.**
I recommend keeping the value close to the default of 20 minutes.
Mine is `35` minutes.
When you finish your daily reviews and new cards,
Anki will start ignoring intervals of cards in the learning queue `less` than
this value and showing the cards to you right away.
This is good for cards with small intervals because it lets you finish your reps
without breaking the flow and waiting for your cards to become ready to be reviewed.
But if you set the `Learn ahead limit` too high
cards with longer learning steps will be shown to you too early.
Keeping the value on the lower side enforces the wait time of your steps.
If you set this to `0`, Anki will always wait the full delay, so it's not optimal either.

* **Show new cards after reviews.**
You always want to finish your reviews first,
and you don’t want new cards to slow you down. You can choose `Show new cards before reviews`
if you are consistent and feel confident that you will never have a backlog of Anki reviews.
Mixing is probably the worst way and will confuse you when
a new card pops up after a streak of mature cards.

* **Anki 2021 scheduler.**
This is a
[new scheduler](https://faqs.ankiweb.net/the-2021-scheduler.html)
that comes with Anki 2.1.45+.
If your version of Anki doesn't show this option, it has been already enabled by default.
Otherwise, make sure to enable it.
The old `V1` scheduler was buggy and clunky.
The new one fixes its issues.

    Main killer features:
    * You can have subdecks and review all of them at once,
    the cards will be properly mixed when reviewing.
    * You can learn new cards in filtered decks.
    Filtered decks no longer reset learning steps when rebuilt or emptied.

<p align="center"><img alt="preferences" class="shadow" src="img/anki-preferences.webp"></p>

### Options Groups

Each deck has an Options Group attached to it.
The subdeck options will override the parent deck options.
Click `Deck > Options` to access Options Groups settings.
You can hit Manage to create additional options groups.

**Warning:** If you're running Anki 2.1.45+,
you will be presented with a new Options Groups settings dialog.
As usual, Anki developers are making the app worse with each release.
The new layout won't match with the screenshots shown on this page.
If you want to bring up the old version of the dialog,
click "Deck Options" while holding `Shift`.

Below are the options I recommended using.

<details>

<summary>New menu</summary>

The new Options Groups settings menu
can be seen on Anki starting from 2.1.45.
The options are described later in this article.

<p align="center"><img alt="options groups" src="img/anki-options-groups.webp"></p>
<p align="center"><i>Settings.</i></p>

</details>

#### New cards

* **Steps (in minutes):** This is the number of times you have to answer `good` on the card
    before it graduates.
    I recommend beginners to stick to the default learning steps of `1 10`.
    When you get more familiar with Anki you can add your custom steps and experiment with them.
    But don't overdo it: too many steps will make you spend too much time in Anki
    for no substantial gain in retention.
    The `learn ahead` option set in the previous section
    will make sure that you won't be shown cards with custom steps too early.

    You can experiment with so-called micro steps
    if you see that remembering new cards is more difficult than you thought.
    This means specifying an interval in seconds instead of minutes.
    For the new settings menu you just type `30s` for 30 seconds.
    For the old menu you need to specify a decimal like this: `0.5`.

* **New cards/day:** The default value of `20` cards is very reasonable and manageable for most users.
    However, if you feel overwhelmed by the amount of reviews you have to do,
    lower it to about `10` new cards a day.
    Doing more cards is also possible if you can keep up with the review load,
    but generally in the AJATT community it is advised to learn no more than `30` new cards a day.

    As you've noticed, I keep my setting at `0`. That's simply because I use the
    [Learn now Button](https://ankiweb.net/shared/info/1021636467)
    add-on to **manually pick** and learn cards from my Sentence Bank.

* **Starting ease:** Set it to `131%` and you won't have to worry about Ease at all.
    Ease is very nasty because by default it gradually decreases when you fail cards
    or answer "Hard" on them.
    This leads to intervals growing slower, and eventually you fall into **Ease Hell**.
    Similarly, pressing "Easy" causes the Ease to increase.
    It drags the cards' intervals along causing them to grow faster than normal,
    which leads to forgetting in the future.

	* If you've been using Anki before applying this setting, you should *refold* your collection
	with the [RefoldEase](https://ankiweb.net/shared/info/819023663) add-on.
	* If you would like to learn more about Ease Hell, watch
	[this video](https://redirect.invidious.io/watch?v=1XaJjbCSXT0).

<p align="center"><img alt="new cards" class="shadow" src="img/options-groups-new-cards.webp"></p>

#### Reviews

* **Maximum reviews/day:** This value sets an arbitrary cap on the amount of reviews you can do each day.
If the cap is low, your due cards won't magically disappear after you've done with the reviews.
Instead they will form a backlog of likely forgotten cards.
Because you want to review all your due cards every day,
set this at a high value.

* **Interval modifier:** Now here is where it gets interesting.
    When you answer **Good** on a card, its interval is recalculated:
    ```
    New interval = current interval * Card's ease * Interval Modifier
    ```
    By default, new interval is `2.5 * last interval`.
    At its default value of 100%, `Interval Modifier` does nothing.
    However, this is not what you want
    because you've just lowered `Starting Ease` to 131% in the previous step.
    To restore the balance bump `Interval Modifier` up to 192%.
    `1.92 * 1.31` is roughly equal to `2.5`.
    Later after you've used Anki for a couple of months and have had high retention,
    you can increase the value further and do less reviews.
    If you forget too many cards, it is recommended to lower it a bit.

    If you've used the [RefoldEase](https://ankiweb.net/shared/info/819023663) add-on
    from the previous step, your `Interval Modifier` should be already set to the right value.

* **Easy bonus** and **Hard interval**: Ignore these settings as you should never use
the “hard” and “easy” buttons.

    <p align="center"><img alt="hard-easy" class="shadow" src="img/anki-buttons.webp"></p>

    As I mentioned in the `Starting ease` section,
    the “hard” and “easy” buttons have counter-intuitive effects on Anki’s algorithm,
    which causes long-term problems with Ease of your cards.

* **Maximum interval:** Intervals of your cards can never increase beyond this limit.
    I advise setting it as big as possible.
    The default is `36500` days, which is equal to `100` years.
    However, you can decrease this to a smaller number if you want to ensure long-term retention.

<p align="center"><img alt="reviews" class="shadow" src="img/options-groups-reviews.webp"></p>

#### Lapses

* **Steps (in minutes):**
    Works similar to the setting in the `New Cards` tab,
    except it’s for cards you've pressed “Again” on.
    It affects how well you will relearn your lapsed cards.
    Beginners should set one learning step and observe their experience.
    The default of `10` minutes is okay but I prefer a slightly bigger one.
    Later you can experiment with more learning steps.

* **New interval:**
    You often still somewhat remember a word in Japanese even if you fail it.
    A different context or another word, or studying it on a different day may jog your memory.
    Thus we don’t need to fully penalize a fail here.

    I use a new interval of 55% so as to not completely reset a card to 0.
    The recommended range in the AJATT community is between 50 and 75%.

    For a word cards deck you may set it to about 30-40%
    because word cards are noticeably harder than sentence cards.

* **Leech threshold** and **Leech action**:
    *Leeches* are cards that you keep on forgetting and relearning over and over.
    Keep the leech threshold low (4-6 lapses) and suspend the cards when they become leeches.
    You have to properly deal with leeches instead of letting them rotate in your deck and slow you down.

    Possible ways to deal with leeches:

    * **Delete them:** For those small minority of cards that just won’t stick,
    it’s best to just get rid of them. Instead of wasting a bunch of time on a single leech,
    it’s more productive to learn 5 normal cards in its place.

    * **Keep them for later:** If you can't remember a word after 4-5 lapses,
    it means that your brain hasn't been primed yet to acquire it.
    Wait a month or two and try again.
    Often you'll find that cards that wouldn't stick before had become very easy.

    * **Make a new card for the same target word:** If a word is of high value to you,
    you can try to memorize a
    [different representation](https://www.supermemo.com/de/archives1990-2015/articles/20rules)
    of it.
    Find a different example sentence in your Sentence Bank or online.
    For example, on [weblio](https://ejje.weblio.jp/sentence/).

<p align="center"><img alt="lapses" class="shadow" src="img/options-groups-lapses.webp"></p>

## GTK theme

Anki uses the
[Qt](https://wiki.archlinux.org/title/Qt)
toolkit.
To tell Anki to use your GTK theme,
install
[qt5-styleplugins](https://aur.archlinux.org/packages/qt5-styleplugins/)
and set the following
[environment variable](https://wiki.archlinux.org/title/Environment_variables#Graphical_environment):

```
export QT_QPA_PLATFORMTHEME=gtk2
```

Then relogin or reboot.

## Trying different versions

If you want to install and test multiple versions of Anki at the same time,
use the following functions.
Add them to your
[~/.bashrc](https://wiki.archlinux.org/title/Bash#Configuration_files)
or
[~/.zshrc](https://wiki.archlinux.org/title/Zsh#Configure_Zsh).

Install a specific version.
For example, run `anki_test_install 45` to install Anki `2.1.45`.

```
anki_test_install() {
	local -r version=${1:?No version provided.}
	local -r dir=~/.local/share/anki_builds/"anki_$version"
	(
		mkdir -p -- "$dir" && cd -- "$dir" || exit
		python -m venv --system-site-packages pyenv
		./pyenv/bin/pip3 install --upgrade pip
		./pyenv/bin/pip3 install --upgrade --pre "aqt==2.1.$version"
	)
}
```

Run a specific version.
This script uses [dmenu](https://wiki.archlinux.org/title/Dmenu) to ask what version you want to run.

```
anki_test_run() {
	local -r dir=~/.local/share/anki_builds
	if [[ $* ]]; then
		local -r choice=$*
	else
		local -r choice=$(ls -1 "$dir" | dmenu)
	fi
	if [[ -n $choice ]]; then
		(cd -- "$dir/$choice" && ./pyenv/bin/anki)
	fi
}
```

These functions are
[available on my GitHub](https://github.com/tatsumoto-ren/dotfiles/blob/main/.config/shell/functionrc).

Tags: anki
