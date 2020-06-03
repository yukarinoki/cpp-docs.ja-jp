---
title: LINK の入力ファイル
ms.date: 11/04/2016
helpviewer_keywords:
- files [C++], LINK
- module definition files
- resources [C++], linker files
- LINK tool [C++], input files
- module definition files, linker files
- input files [C++], LINK
- linker [C++], input files
- import libraries [C++], linker files
- command input to linker files [C++]
ms.assetid: bb26fcc5-509a-4620-bc3e-b6c6e603a412
ms.openlocfilehash: aec71d4622821618f377953d36a9676e2233eefc
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81328197"
---
# <a name="link-input-files"></a>LINK の入力ファイル

リンカーには、オブジェクト、インポートライブラリ、標準ライブラリ、リソース、モジュール定義、およびコマンド入力を含むファイルを指定します。 LINK では、ファイルの内容を前提としてファイル拡張子を使用することはありません。 代わりに、LINK は各入力ファイルを調べて、ファイルの種類を判別します。

コマンド ライン上のオブジェクト ファイルは、コマンド ラインに表示される順序で処理されます。 ライブラリはコマンド ラインの順序でも検索され、次の注意事項があります: ライブラリからオブジェクト ファイルを取り込むときに未解決のシンボルは、最初にそのライブラリで検索され、次にコマンド ラインと[/DEFAULTLIB (既定のライブラリの指定)](defaultlib-specify-default-library.md)ディレクティブから次のライブラリを検索し、次にコマンド ラインの先頭にある任意のライブラリに検索します。

> [!NOTE]
> LINK は、応答ファイルおよび注文ファイルのコメントの先頭としてセミコロン (またはその他の文字) を受け入れなくなりました。 セミコロンは、モジュール定義ファイル (.def) 内のコメントの開始としてのみ認識されます。

LINK では、次のタイプの入力ファイルを使用します。

- [.obj ファイル](dot-obj-files-as-linker-input.md)

- [.net モジュール ファイル](netmodule-files-as-linker-input.md)

- [.lib ファイル](dot-lib-files-as-linker-input.md)

- [.exp ファイル](dot-exp-files-as-linker-input.md)

- [.def ファイル](dot-def-files-as-linker-input.md)

- [.pdb ファイル](dot-pdb-files-as-linker-input.md)

- [.res ファイル](dot-res-files-as-linker-input.md)

- [.exe ファイル](dot-exe-files-as-linker-input.md)

- [.txt ファイル](dot-txt-files-as-linker-input.md)

- [.ilk ファイル](dot-ilk-files-as-linker-input.md)

## <a name="see-also"></a>関連項目

[MSVC リンカーのリファレンス](linking.md)<br/>
[MSVC リンカー オプション](linker-options.md)
