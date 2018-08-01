---
title: jitintrinsic |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- jitintrinsic
- jitintrinsic_cpp
dev_langs:
- C++
helpviewer_keywords:
- __declspec keyword [C++], jitintrinsic
- jitintrinsic __declspec modifier
ms.assetid: 23dbe416-7ef6-442b-b16d-9a81aab04fa6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f0b114089567de06a71f15b69c556e08d1e4e9c6
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/01/2018
ms.locfileid: "39404081"
---
# <a name="jitintrinsic"></a>jitintrinsic
64 ビット共通言語ランタイムにとって重要であると関数をマークします。 これは、Microsoft が提供するライブラリの特定の関数で使用されます。  
  
## <a name="syntax"></a>構文  
  
```  
__declspec(jitintrinsic)  
```  
  
## <a name="remarks"></a>Remarks  
 **jitintrinsic** MODOPT を追加します (<xref:System.Runtime.CompilerServices.IsJitIntrinsic>) 関数のシグネチャにします。  
  
 ユーザーはこれを使用してから推奨されません **_ _declspec**修飾子は、予期しない結果として発生することができます。  
  
## <a name="see-also"></a>関連項目  
 [__declspec](../cpp/declspec.md)   
 [キーワード](../cpp/keywords-cpp.md)