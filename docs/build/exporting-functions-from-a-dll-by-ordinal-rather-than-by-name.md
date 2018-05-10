---
title: 名前ではなく序数で DLL から関数をエクスポートする |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
f1_keywords:
- NONAME
dev_langs:
- C++
helpviewer_keywords:
- exporting functions [C++], ordinal values
- ordinal exports [C++]
- exporting DLLs [C++], ordinal values
- NONAME attribute
ms.assetid: 679719fd-d965-4df3-9f7a-7d86ad831702
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b05f3e429406b3c24c7a21ce9ee8e10fe19c14b8
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="exporting-functions-from-a-dll-by-ordinal-rather-than-by-name"></a>名前ではなく序数値による DLL 関数のエクスポート
DLL から関数をエクスポートする最も簡単な方法では、名前によるエクスポートです。 これは、使用するときに起こる**方式**、例を示します。 代わりに序数で関数をエクスポートすることができます。 この手法を使用する必要がありますの代わりに .def ファイルを使用して**方式**です。 関数の序数値を指定するには、.def ファイル内の関数名をその序数を追加します。 序数値の指定方法の詳細については、次を参照してください。 [.def ファイルを使った DLL からエクスポートする](../build/exporting-from-a-dll-using-def-files.md)です。  
  
> [!TIP]
>  DLL のファイルのサイズを最適化する場合は、使用、 **NONAME**エクスポートされた各関数の属性です。 **NONAME**属性、序数に格納されている場合、DLL のエクスポート関数名ではなくテーブル。 多くの関数をエクスポートする場合は、大幅なコスト削減にできます。  
  
## <a name="what-do-you-want-to-do"></a>実行する操作  
  
-   [序数でエクスポートできるように、.def ファイルを使用します。](../build/exporting-from-a-dll-using-def-files.md)  
  
-   [関数を使用します。](../build/exporting-from-a-dll-using-declspec-dllexport.md)  
  
## <a name="see-also"></a>関連項目  
 [DLL からのエクスポート](../build/exporting-from-a-dll.md)