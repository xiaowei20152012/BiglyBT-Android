# BiglyBT

Source for BiglyBT, a feature filled, open source, ad-free, bittorrent client.  BiglyBT is forked from Vuze/Azureus and is being maintained by two of the original developers as well as members of the community.  With over 15 years of development, there's a good chance we have the features you are looking for, as well as the decade old bugs you aren't looking for :)

* [Official BiglyBT site](https://www.biglybt.com)
* [Ways to Contribute](CONTRIBUTING.md)
* [Translation Information](TRANSLATE.md)
* [Feature Voting Page](https://vote.biglybt.com)
* [Coding Guidelines](CODING_GUIDELINES.md)

## Donations


| Method | Address |
|:--|:--|
| PayPal | [BiglyBT's Donation Page](https://www.biglybt.com/donation/donate.php) |
| BCH/BTC/BSG/BSV | 1BiGLYBT38ttJhvZkjGc5mCw5uKoRHcUmr |
| DASH            | XjDwmSrDPQBaLzCkuRHZaFzHf7mTVxkW9K |
| DOGE | DMXWdEtPUJc5p2sbHGo77SvqFXKTR8Vff1 |
| ETH/ETC | 0x4e609B5EF88C8aA8Ab73945fD1ba68c9E27faC75 |
| LTC | LKGc2utCrGfojpYsX3naT9n1AxjLiZ5MMG |
| TRX/BTT | TAbsb7pjEEWNpXFvPf49rfVhFSB2e3dAM7 |
| XRP | rPFKfbx2tuzMMaz7Zy99M6CquHKgp9srSb |

## Setting up Dev Environment

Getting the basics to compile from source is pretty straightforward:

1. Clone the repo into your favorite IDE
1. Mark `core/src` and `uis/src` as project roots (source modules)
1. To the uis module, add `core/lib/*` and one of the swt.jars at `/uis/lib/`:<br>
  `swt-win64.jar` on Windows<br>
  `swt-cocoa-64.jar` on OSX<br>
  `swt-linux-64.jar` on Linux (GTK)
1. To the core module, add `core/lib/*`
1. Make `uis` module depend on `core`.  `Core` should not depend on `uis`

IntelliJ IDEA will do all these steps for you with its wizard.

### External Annotations

If you wish IntelliJ IDEA to show MessageBundle strings instead of keys, as well as reduce the number of NPE warnings, you can attach the external annotations either by:
* Project Settings->Modules->Paths->External Annotations
*  in `<module>/<module>.iml` add to component:
    ```
    <annotation-paths>
      <root url="file://$MODULE_DIR$/../external-annotations" />
    </annotation-paths>
    ```
External Annotations definitions are a WIP and not complete list of definitions.

## Running in Dev Environment

Running is only few more steps:

* Main class is `com.biglybt.ui.Main` in module `uis`
* Working Directory should be a new folder, since the app will write things to it. Put the `aereg.dll` or `libOSXAccess.jnilib` in there.
  
  When a normal user is running the app, the working directory is where the jar, executable, and libraries (dll, so, jnilib) are.
* If you want a separate config dir from the default one, use VM Option `-Dazureus.config.path=<some config path>`
* Run it

## Release Installer Notes

We build our installers using [Install4j, multi-platform installer builder](https://www.ej-technologies.com/products/install4j/overview.html)

![Install4j Logo](https://www.ej-technologies.com/images/product_banners/install4j_large.png)

<!--  1.3.2.0 -->

<!--  8caad2b9b54ae45938150c7920c7a7587eefaa8a Android-DirectoryChooser (v3.2-46-g8caad2b) -->
<!--  ed1c82ef6226a3deb92853fb70bdbb509f8c323f BiglyBT-plugin-aercm (ed1c82e) -->
<!--  b430cb8098061d238aabfc3240a3dbba5d6e144a BiglyBT-plugin-azutp (b430cb8) -->
<!--  a74e46b70cfd56009267e0f20a90cb00dbbb74a4 BiglyBT-plugin-mlDHT (remotes/origin/android) -->
<!--  d8020c96f1e66e691b2d5328c3728e6fdb49a829 BiglyBT-plugin-xmwebui (d8020c9) -->
<!--  526927114c9b64ccc76e64a1e97ee76753624de0 core (v2.6.0.0-155-g52692711) -->
<!--  58c946f0c70c5844cbe6798533b361ff036296f0 mldht (old_indexer-394-g58c946f) -->


