---
description: '詳細情報: インラインファイルの指定'
title: インライン ファイルの指定
ms.date: 11/04/2016
helpviewer_keywords:
- NMAKE program, inline files
- inline files [C++], specifying NMAKE
- files [C++], inline
ms.assetid: 393eccfb-3fc9-4bac-a30c-8ac8d221cca3
ms.openlocfilehash: 461bf507f707512aa690e81dc5752a97d0c1c4ce
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97224609"
---
# <a name="specifying-an-inline-file"></a>インライン ファイルの指定

*Filename* を表示するコマンドに2つの山かっこ (<<) を指定します。 山かっこをマクロ展開にすることはできません。

## <a name="syntax"></a>構文

```
<<[filename]
```

## <a name="remarks"></a>解説

コマンドが実行されると、山かっこは、指定されている場合は *filename* に置き換えられ、NMAKE によって生成された一意の名前で置換されます。 指定した場合、 *ファイル名* はスペースまたはタブなしで山かっこに従う必要があります。パスは許可されています。 拡張子は必要ないか、想定されていません。 *Filename* が指定されている場合、ファイルは現在のディレクトリまたは指定されたディレクトリに作成され、その名前によって既存のファイルが上書きされます。それ以外の場合は、TMP ディレクトリ (TMP 環境変数が定義されていない場合は現在のディレクトリ) に作成されます。 以前のファイル *名* を再利用すると、NMAKE によって前のファイルが置き換えられます。

## <a name="see-also"></a>関連項目

[メイクファイルのインラインファイル](inline-files-in-a-makefile.md)
