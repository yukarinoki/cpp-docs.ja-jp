---
title: _Declspec を使ったデータのインポート |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
f1_keywords:
- dllimport
dev_langs:
- C++
helpviewer_keywords:
- importing data [C++]
- dllimport attribute [C++], data imports
- __declspec(dllimport) keyword [C++]
- importing DLLs [C++], __declspec(dllimport)
ms.assetid: 0ae70b39-87c7-4181-8be9-e786e0db60b0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a024d7488eb1683f40548839ab843da1e56f65e8
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45710217"
---
# <a name="importing-data-using-declspecdllimport"></a>__declspec(dllimport) を使ったデータのインポート

使用して、データの場合は **_declspec**は間接レイヤーの役割を削除する便利な項目です。 DLL からデータをインポートするときにも、インポート アドレス テーブルを通じて行う必要があります。 前に **_declspec**、つまり、DLL からエクスポートされたデータにアクセスするときに、追加のレベルの間接参照を実行する必要があります。

```
// project.h
#ifdef _DLL   // If accessing the data from inside the DLL
   ULONG ulDataInDll;

#else         // If accessing the data from outside the DLL
   ULONG *ulDataInDll;
#endif
```

内のデータをエクスポートしは、します。DEF ファイル:

```
// project.def
LIBRARY project
EXPORTS
   ulDataInDll   CONSTANT
```

DLL の外部のアクセスします。

```
if (*ulDataInDll == 0L)
{
   // Do stuff here
}
```

データとしてマークすると **_declspec**コンパイラは、の間接参照コードを自動的に生成されます。 不要になった、上記の手順について心配する必要があるとします。 既に説明したようには使用しないでください **_declspec** DLL のビルド時にデータを宣言します。 DLL 内の関数では、データ オブジェクトにアクセスするのにインポート アドレス テーブルを使用しないでください。そのため、余分な間接参照が存在するレベルはありません。

DLL から自動的にデータをエクスポートするには、この宣言を使用します。

```
__declspec(dllexport) ULONG ulDataInDLL;
```

## <a name="see-also"></a>関連項目

[アプリケーションへのインポート](../build/importing-into-an-application.md)