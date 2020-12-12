---
description: 詳細情報:/バインド
title: /BIND
ms.date: 11/04/2016
f1_keywords:
- /bind
helpviewer_keywords:
- -BIND editbin option
- entry points, addresses
- BIND editbin option
- entry points
- /BIND editbin option
- import address table
ms.assetid: 3772b330-1868-4c90-857d-c31faa867982
ms.openlocfilehash: 87ea0265555991fca019760feec4395692c074ae
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97187144"
---
# <a name="bind"></a>/BIND

```
/BIND[:PATH=path]
```

## <a name="remarks"></a>解説

このオプションは、実行可能ファイルまたは DLL のインポートアドレステーブル内のエントリポイントのアドレスを設定します。 プログラムの読み込み時間を短縮するには、このオプションを使用します。

EDITBIN コマンドラインの *files* 引数で、プログラムの実行可能ファイルと dll を指定します。 省略可能な *パス* 引数 (/) は、指定されたファイルで使用される dll の場所を指定します。 複数のディレクトリを区切るには、セミコロン (**;**) を使用します。 *Path* が指定されていない場合、EDITBIN は path 環境変数で指定されたディレクトリを検索します。 *Path* が指定されている場合、EDITBIN は path 変数を無視します。

既定では、プログラムローダーは、プログラムを読み込むときにエントリポイントのアドレスを設定します。 このプロセスの所要時間は、Dll の数とプログラムで参照されているエントリポイントの数によって異なります。 プログラムが/BIND を使用して変更されていて、実行可能ファイルとその Dll のベースアドレスが既に読み込まれている Dll と競合しない場合、オペレーティングシステムはこれらのアドレスを設定する必要はありません。 ファイルが正しく作成されていない状況では、オペレーティングシステムによってプログラムの Dll が再配置され、エントリポイントアドレスが再計算されます。これにより、プログラムの読み込み時間にが追加されます。

## <a name="see-also"></a>関連項目

[EDITBIN オプション](editbin-options.md)
