---
description: 詳細については、「リンク入力ファイル」を参照してください。
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
ms.openlocfilehash: 3bf25d36ab61b35dfe3d1551e9f85e8c2f26862b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97199507"
---
# <a name="link-input-files"></a>LINK の入力ファイル

リンカーには、オブジェクト、インポートと標準ライブラリ、リソース、モジュール定義、およびコマンド入力を含むファイルが用意されています。 リンクはファイルの拡張子を使用せず、ファイルの内容を想定していません。 代わりに、リンクによって各入力ファイルが調べられ、ファイルの種類が決まります。

コマンドライン上のオブジェクトファイルは、コマンドラインに表示される順序で処理されます。 ライブラリはコマンドラインの順序でも検索されますが、次の点に注意してください。ライブラリからオブジェクトファイルを取り込むときに解決されないシンボルは、先にそのライブラリで検索されます。次に、コマンドラインと [/DEFAULTLIB (既定のライブラリの指定)](defaultlib-specify-default-library.md) ディレクティブから次のライブラリを検索し、コマンドラインの先頭にある任意のライブラリ

> [!NOTE]
> リンクは、応答ファイルと注文ファイルのコメントの先頭として、セミコロン (またはその他の文字) を受け付けなくなりました。 セミコロンは、モジュール定義ファイル (.def) のコメントの先頭としてのみ認識されます。

リンクでは、次の種類の入力ファイルが使用されます。

- [.obj ファイル](dot-obj-files-as-linker-input.md)

- [.netmodule ファイル](netmodule-files-as-linker-input.md)

- [.lib ファイル](dot-lib-files-as-linker-input.md)

- [.exp ファイル](dot-exp-files-as-linker-input.md)

- [def ファイル](dot-def-files-as-linker-input.md)

- [.pdb ファイル](dot-pdb-files-as-linker-input.md)

- [.res ファイル](dot-res-files-as-linker-input.md)

- [.exe ファイル](dot-exe-files-as-linker-input.md)

- [.txt ファイル](dot-txt-files-as-linker-input.md)

- [.ilk ファイル](dot-ilk-files-as-linker-input.md)

## <a name="see-also"></a>関連項目

[MSVC リンカーのリファレンス](linking.md)<br/>
[MSVC リンカー オプション](linker-options.md)
