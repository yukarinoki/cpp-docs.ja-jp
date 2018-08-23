---
title: raw_method_prefix |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- raw_method_prefix
dev_langs:
- C++
helpviewer_keywords:
- raw_method_prefix attribute
ms.assetid: 71490313-af78-4bb2-b28a-eee67950d30b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8fb9178bc315385bab97cea473430745ad66d973
ms.sourcegitcommit: d4c803bd3a684d7951bf88dcecf1f14af43ae411
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/10/2018
ms.locfileid: "42538437"
---
# <a name="rawmethodprefix"></a>raw_method_prefix
**C++ 固有の仕様**  
  
名前の衝突を避けるために異なるプレフィックスを指定します。  
  
## <a name="syntax"></a>構文  
  
```  
raw_method_prefix("Prefix")  
```  
  
### <a name="parameters"></a>パラメーター  
*Prefix*  
使用されるプレフィックス。  
  
## <a name="remarks"></a>Remarks  
 
低レベルのプロパティとメソッドが既定のプレフィックスを持つという名前のメンバー関数によって公開されている**raw _** 高レベルのエラー処理メンバー関数の名前の競合を回避するためにします。  
  
> [!NOTE]
> 効果、 **raw_method_prefix**の存在によって属性は変更されません、 [raw_interfaces_only](#_predir_raw_interfaces_only)属性。 **Raw_method_prefix**より優先されます`raw_interfaces_only`でプレフィックスを指定します。 両方の属性が同じで使用されている場合`#import`ステートメントでは後で指定されたプレフィックス、 **raw_method_prefix**属性を使用します。  
  
**END C 固有の仕様**  
  
## <a name="see-also"></a>関連項目  
 
[#import の属性](../preprocessor/hash-import-attributes-cpp.md)   
[#import ディレクティブ](../preprocessor/hash-import-directive-cpp.md)