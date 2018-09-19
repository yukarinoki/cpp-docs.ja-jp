---
title: 環境変数 LINK |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- link
dev_langs:
- C++
helpviewer_keywords:
- variables, environment
- LINK tool [C++], environment variables
- LIB environment variable
- environment variables [C++], LINK
ms.assetid: 9a3d3291-0cc4-4a7d-9d50-80e351b90708
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e88ac63ace95ac0b9874dc3376210f3f5b4af320
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45716655"
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
