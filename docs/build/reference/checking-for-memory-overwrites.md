---
title: メモリ上書きのチェック |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- memory, overwrites
ms.assetid: da7c5d77-a267-415f-a8ab-ee5ce5bfc286
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 258aa6ae01d48df6717135f7dc8b73fc3f9e697a
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32369852"
---
# <a name="checking-for-memory-overwrites"></a>メモリ上書きのチェック
ヒープ操作関数への呼び出しでアクセス違反が発生する場合は、可能であれば、プログラムによって、ヒープが破損していること。 このような状況の一般的な症状は次のようになります。  
  
```  
Access Violation in _searchseg  
```  
  
 [_Heapchk](../../c-runtime-library/reference/heapchk.md)関数は、両方のデバッグで使用可能なビルドとリリース ビルド (Windows NT のみ) のランタイム ライブラリのヒープの整合性を検証します。 使用することができます`_heapchk`とほぼ同じ方法で、`AfxCheckMemory`たとえば、ヒープの上書きを分離する関数。  
  
```  
if(_heapchk()!=_HEAPOK)  
   DebugBreak();  
```  
  
 この関数が失敗した場合、する必要がありますを特定するこの時点で、ヒープが破損しています。  
  
## <a name="see-also"></a>関連項目  
 [リリース ビルドの問題の解決](../../build/reference/fixing-release-build-problems.md)