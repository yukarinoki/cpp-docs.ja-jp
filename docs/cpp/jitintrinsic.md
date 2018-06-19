---
title: jitintrinsic |Microsoft ドキュメント
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
ms.openlocfilehash: 71cd88882ea104275e4c1a43ccf05494a859d303
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32418755"
---
# <a name="jitintrinsic"></a>jitintrinsic
64 ビット共通言語ランタイムにとって重要であると関数をマークします。 これは、Microsoft が提供するライブラリの特定の関数で使用されます。  
  
## <a name="syntax"></a>構文  
  
```  
__declspec(jitintrinsic)  
```  
  
## <a name="remarks"></a>コメント  
 `jitintrinsic` は、関数シグネチャに MODOPT (<xref:System.Runtime.CompilerServices.IsJitIntrinsic>) を追加します。  
  
 予期しない結果が発生する可能性があるため、ユーザーはこの `__declspec` 修飾子を使用しないでください。  
  
## <a name="see-also"></a>関連項目  
 [__declspec](../cpp/declspec.md)   
 [キーワード](../cpp/keywords-cpp.md)