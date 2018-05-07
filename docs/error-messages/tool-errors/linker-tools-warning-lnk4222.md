---
title: リンカー ツールの警告 LNK4222 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4222
dev_langs:
- C++
helpviewer_keywords:
- LNK4222
ms.assetid: b7bb1794-41fb-4c83-b9b0-59c0d786a7da
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 359af4c4d3b1079b2d56f108bff0ee1488ea71f9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="linker-tools-warning-lnk4222"></a>リンカー ツールの警告 LNK4222
エクスポートされたシンボル 'symbol' に序数を割り当てないでください。  
  
 次の記号を序数でエクスポートされない必要があります。  
  
-   `DllCanUnloadNow`  
  
-   `DllGetClassObject`  
  
-   `DllGetClassFactoryFromClassString`  
  
-   `DllInstall`  
  
-   `DllRegisterServer`  
  
-   `DllRegisterServerEx`  
  
-   `DllUnregisterServer`  
  
 これらの関数は、名前で常にあるを使用して`GetProcAddress`です。 これに関する注意事項について、リンカーはイメージが大きくなる可能性があるために、エクスポートの種類。 これは、序数でのエクスポートの範囲は比較的少数のエクスポートを含む大規模な場合に発生する可能性があります。 たとえば、オブジェクトに適用された  
  
```  
EXPORTS  
   DllGetClassObject   @1  
   MyOtherAPI      @100  
```  
  
 (2 ~ 99) は単なる空白はそのうちの 98 エクスポート アドレス テーブルで 100 のスロットを必要となります。 反対に  
  
```  
EXPORTS  
   DllGetClassObject  
   MyOtherAPI      @100  
```  
  
 2 つのスロットを必要となります。 (でもエクスポートできることに注意してください、 [/export](../../build/reference/export-exports-a-function.md)リンカー オプションです)。