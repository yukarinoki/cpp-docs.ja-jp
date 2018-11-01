---
title: 環境変数 LINK
ms.date: 11/04/2016
f1_keywords:
- link
helpviewer_keywords:
- variables, environment
- LINK tool [C++], environment variables
- LIB environment variable
- environment variables [C++], LINK
ms.assetid: 9a3d3291-0cc4-4a7d-9d50-80e351b90708
ms.openlocfilehash: 3a398787530794f5a08d6cd122e55c305e265062
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50434412"
---
# <a name="link-environment-variables"></a>環境変数 LINK

LINK ツールでは、次の環境変数を使用します。

- リンクと\_リンク\_、定義されている場合。 定義されている引数およびリンク ツール オプションと環境変数 LINK に定義されている引数の前に付加し、オプションを追加します、\_リンク\_環境変数を処理する前にコマンドライン引数。

- LIB。定義されている場合。 LINK ツールは、オブジェクト、ライブラリ、またはコマンドラインでまたはを指定されたその他のファイルを検索するときに LIB パスを使用、 [/base](../../build/reference/base-base-address.md)オプション。 また、オブジェクトで指定された .pdb ファイルを検索するときにも LIB パスを使用します。 LIB 変数では、複数のパスをセミコロンで区切って指定できます。 1 つのパスは Visual C++ インストールの \lib サブディレクトリを示す必要があります。

- PATH。ツールが CVTRES を実行する必要があり、LINK 自身と同じディレクトリ内にこのファイルが見つからない場合  (LINK では、.res ファイルをリンクするために CVTRES を必要とします)。PATH は Visual C++ インストールの \bin サブディレクトリを示す必要があります。

- TMP。OMF ファイルまたは .res ファイルをリンクするときのディレクトリを指定します。

## <a name="see-also"></a>関連項目

[リンカー オプションの設定](../../build/reference/setting-linker-options.md)<br/>
[リンカー オプション](../../build/reference/linker-options.md)<br/>
[コマンドラインでの C/C++ コードのビルド](../../build/building-on-the-command-line.md)<br/>
[コマンド ライン ビルドのパスと環境変数の設定](../../build/setting-the-path-and-environment-variables-for-command-line-builds.md)
