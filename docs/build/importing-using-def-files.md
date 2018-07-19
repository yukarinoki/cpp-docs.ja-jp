---
title: DEF ファイルを使用したインポート |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- importing DLLs [C++], DEF files
- def files [C++], importing with
- .def files [C++], importing with
- dllimport attribute [C++], DEF files
- DLLs [C++], DEF files
ms.assetid: aefdbf50-f603-488a-b0d7-ed737bae311d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b36a68267251f76294ec6f3a0391ffa5f259704c
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32368858"
---
# <a name="importing-using-def-files"></a>DEF ファイルを使ったインポート
使用する場合 **_declspec (dllimport)** .def ファイルと共に、定数の代わりにデータを使用して、コーディングの誤りは、問題の原因の可能性を低く .def ファイルを変更する必要があります。  
  
```  
// project.def  
LIBRARY project  
EXPORTS  
   ulDataInDll   DATA  
```  
  
 次の表は、理由を示しています。  
  
|キーワード|インポート ライブラリに出力します。|エクスポート|  
|-------------|---------------------------------|-------------|  
|`CONSTANT`|`_imp_ulDataInDll`, `_ulDataInDll`|`_ulDataInDll`|  
|`DATA`|`_imp_ulDataInDll`|`_ulDataInDll`|  
  
 使用して **_declspec (dllimport)** 定数はどちらも一覧表示し、`imp`バージョンと非装飾名 .lib DLL では、明示的なリンクを許可するために作成したライブラリをインポートします。 使用して **_declspec**およびデータの一覧だけを`imp`名のバージョン。  
  
 コード構文を次のいずれかの使用できる定数を使用する場合にアクセスする`ulDataInDll`:  
  
```  
__declspec(dllimport) ULONG ulDataInDll; /*prototype*/  
if (ulDataInDll == 0L)   /*sample code fragment*/  
```  
  
 - または -  
  
```  
ULONG *ulDataInDll;      /*prototype*/  
if (*ulDataInDll == 0L)  /*sample code fragment*/  
```  
  
 ただし、.def ファイルにデータを使用する場合、次の定義でコンパイルされたコードのみ変数にアクセスできる`ulDataInDll`:  
  
```  
__declspec(dllimport) ULONG ulDataInDll;  
  
if (ulDataInDll == 0L)   /*sample code fragment*/  
```  
  
 使用する定数はリスクの高い変数へのインポート アドレス テーブルのポインターにアクセスする忘れた場合は余分なレベルの間接参照を使用する、可能性のあるでした — 変数自体ではありません。 インポート アドレス テーブルは現在読み取り専用にして、コンパイラとリンカーのため、この種の問題のマニフェストはアクセス違反として多くの場合、ことができます。  
  
 現在の Visual C リンカーは、この場合のために .def ファイル内の定数が場合に警告を発行します。 定数を使用する唯一の理由がのかどうか、一部のオブジェクト ファイル、ヘッダー ファイルが一覧表示されませんが再コンパイルできません **_declspec (dllimport)** プロトタイプ。  
  
## <a name="see-also"></a>関連項目  
 [アプリケーションへのインポート](../build/importing-into-an-application.md)
