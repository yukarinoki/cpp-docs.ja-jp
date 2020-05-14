---
title: __declspec(dllimport) を使ったデータのインポート
ms.date: 11/04/2016
helpviewer_keywords:
- importing data [C++]
- dllimport attribute [C++], data imports
- __declspec(dllimport) keyword [C++]
- importing DLLs [C++], __declspec(dllimport)
ms.assetid: 0ae70b39-87c7-4181-8be9-e786e0db60b0
ms.openlocfilehash: c9dce798572a91bcb9721f022393abb669970131
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2020
ms.locfileid: "79440445"
---
# <a name="importing-data-using-__declspecdllimport"></a>__declspec(dllimport) を使ったデータのインポート

データの場合、 **__declspec (dllimport)** の使用は、間接参照の層を削除する便利な項目になります。 DLL からデータをインポートする場合は、引き続きインポート アドレス テーブルを参照する必要があります。 **__declspec(dllimport)** の前は、これは、DLL からエクスポートされたデータにアクセスするときに、追加のレベルの間接参照を忘れずに実行する必要があることを意味していました。

```
// project.h
#ifdef _DLL   // If accessing the data from inside the DLL
   ULONG ulDataInDll;

#else         // If accessing the data from outside the DLL
   ULONG *ulDataInDll;
#endif
```

その後、データを DEF ファイルにエクスポートし、

```
// project.def
LIBRARY project
EXPORTS
   ulDataInDll   CONSTANT
```

DLL の外部でそれにアクセスします。

```
if (*ulDataInDll == 0L)
{
   // Do stuff here
}
```

データを **__declspec (dllimport)** とマークすると、コンパイラによって間接参照コードが自動的に生成されます。 上記の手順について心配する必要はなくなります。 前述したように、DLL をビルドするときに、データに対して **__declspec (dllimport)** 宣言を使用しないでください。 DLL 内の関数では、データ オブジェクトにアクセスするためにインポート アドレス テーブルは使用されません。したがって、追加レベルの間接参照は存在しません。

DLL からデータを自動的にエクスポートするには、次の宣言を使用します。

```
__declspec(dllexport) ULONG ulDataInDLL;
```

## <a name="see-also"></a>関連項目

[アプリケーションへのインポート](importing-into-an-application.md)
