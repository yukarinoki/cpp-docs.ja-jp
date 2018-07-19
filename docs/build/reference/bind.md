---
title: -BIND |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /bind
dev_langs:
- C++
helpviewer_keywords:
- -BIND editbin option
- entry points, addresses
- BIND editbin option
- entry points
- /BIND editbin option
- import address table
ms.assetid: 3772b330-1868-4c90-857d-c31faa867982
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b77c778017dc78235948e8d23db136c1f63ab12d
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32372436"
---
# <a name="bind"></a>/BIND
```  
/BIND[:PATH=path]  
```  
  
## <a name="remarks"></a>コメント  
 このオプションは、実行可能ファイルまたは DLL のインポート アドレス テーブルにエントリ ポイントのアドレスを設定します。 このオプションを使用すると、プログラムの読み込み時間を短縮できます。  
  
 プログラムの実行可能ファイルとで Dll を指定、*ファイル*EDITBIN コマンドラインの引数。 省略可能な*パス*/BIND への引数が指定されたファイルによって使用されている Dll の場所を指定します。 複数のディレクトリをセミコロンで区切ります (**;**)。 場合*パス*が指定されていない、EDITBIN が PATH 環境変数で指定されたディレクトリを検索します。 場合*パス*を指定すると、EDITBIN パス変数は無視されます。  
  
 既定は、プログラムのローダーは、プログラムを読み込むときに、エントリ ポイントのアドレスを設定します。 このプロセスにかかる時間の量は、Dll の数と、プログラムで参照されているエントリ ポイントの数によって異なります。 /Bind、プログラムが変更された場合、および実行可能ファイルのベース アドレスし、その Dll は既に読み込まれている Dll と競合しない場合は、オペレーティング システムがこれらのアドレスを設定する必要はありません。 ここで、ファイルが正しく基づいての状況では、オペレーティング システムは、プログラムの Dll を再配置し、プログラムの読み込み時に追加されるエントリ ポイントのアドレスを再計算されます。  
  
## <a name="see-also"></a>関連項目  
 [EDITBIN オプション](../../build/reference/editbin-options.md)