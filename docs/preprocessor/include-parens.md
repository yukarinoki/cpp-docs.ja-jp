---
title: include() |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- include()
dev_langs:
- C++
helpviewer_keywords:
- include() attribute
ms.assetid: 86c9dcb2-d9e0-4fd5-97d7-0bb3e23d6ecc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ebadd9e453e8a34e92acee363d0dd6b6ff765910
ms.sourcegitcommit: d4c803bd3a684d7951bf88dcecf1f14af43ae411
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/10/2018
ms.locfileid: "42538711"
---
# <a name="include"></a>include()
**C++ 固有の仕様**  
  
自動除外を無効にします。  
  
## <a name="syntax"></a>構文  
  
```  
include("Name1"[,"Name2", ...])  
```  
  
### <a name="parameters"></a>パラメーター  
*Name1*  
強制的に含まれる最初の項目。  
  
*Name2*  
強制的に含める 2 番目の項目 (必要な場合)。  
  
## <a name="remarks"></a>Remarks  
 
タイプ ライブラリは、システム ヘッダーまたはその他のタイプ ライブラリで定義された項目の定義を含むことがあります。 `#import` は、そのような項目を自動的に除外して多重定義エラーを回避します。 示されているアイテムが除外されている場合[コンパイラの警告 (レベル 3) C4192](../error-messages/compiler-warnings/compiler-warning-level-3-c4192.md)、付与しないようにされて、この属性を使用して自動除外を無効にすることができます。 この属性は、任意の数の引数を受け取ることができます。各引数は、含まれるタイプ ライブラリ項目の名前です。  
  
**END C 固有の仕様**  
  
## <a name="see-also"></a>関連項目  
 
[#import の属性](../preprocessor/hash-import-attributes-cpp.md)   
[#import ディレクティブ](../preprocessor/hash-import-directive-cpp.md)