---
title: LINK コマンド ファイル |Microsoft Docs
ms.custom: ''
ms.date: 09/05/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- link
dev_langs:
- C++
helpviewer_keywords:
- syntax, LINK command files
- command files [C++]
- LINK tool [C++]
- text files, passing arguments to LINK
- LINK tool [C++], command-line syntax
- command files [C++], LINK
ms.assetid: 7154511c-32b9-4e5b-a515-3922fa9de48e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2611fc0c16e4ff30d7802989518ca8c5d8dc33af
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45713728"
---
# <a name="link-command-files"></a>LINK コマンド ファイル

コマンド ファイルの形式でリンクには、コマンドライン引数を渡すことができます。 リンカーにコマンド ファイルを指定するには、次の構文を使用します。

> **リンク\@**  <em>commandfile</em>

*Commandfile*テキスト ファイルの名前を指定します。 スペースまたはタブ間は入れません、アット マーク (**\@**) とファイル名。 既定の拡張機能はありません。任意の拡張子を含む完全なファイル名を指定する必要があります。 ワイルドカードを使用することはできません。 ファイル名では、絶対または相対パスを指定できます。 リンクは、ファイルを検索する環境変数を使用しません。

コマンド ファイルで引数で分離できるスペースまたはタブ (コマンドライン) のように、改行文字。

コマンド ファイルでは、コマンドラインの一部またはすべてを指定できます。 LINK コマンドでは、複数のコマンド ファイルを使用することができます。 リンクは、コマンドラインでその場所に指定されたものかのように、コマンド ファイルの入力を受け入れます。 コマンド ファイルを入れ子にすることはできません。 リンクが、コマンド ファイルの内容をエコーしない限り、 [/NOLOGO](../../build/reference/nologo-suppress-startup-banner-linker.md)オプションを指定します。

## <a name="example"></a>例

DLL をビルドするには、次のコマンドは、独立したコマンドのファイルにオブジェクト ファイルとライブラリの名前を渡し、3 番目のコマンド/EXPORTS オプションの指定のファイルを使用します。

```cmd
link /dll @objlist.txt @liblist.txt @exports.txt
```

## <a name="see-also"></a>関連項目

[リンカー オプションの設定](../../build/reference/setting-linker-options.md)<br/>
[リンカー オプション](../../build/reference/linker-options.md)