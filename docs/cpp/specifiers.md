---
title: 指定子 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- declaration specifiers
- declarations, specifiers
- specifiers, in declarations
ms.assetid: 8b14e844-9880-4571-8779-28c8efe44633
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8c1fb739d5e6206297e52fd9103cbba98c5eef01
ms.sourcegitcommit: 7f3df9ff0310a4716b8136ca20deba699ca86c6c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/21/2018
ms.locfileid: "42572290"
---
# <a name="specifiers"></a>指定子
このトピックで説明します、*子*の (宣言指定子) コンポーネント、[宣言](declarations-and-definitions-cpp.md)します。  
  
 次のプレースホルダーと言語キーワードは宣言指定子です。  
  
 *ストレージ クラス指定子*  
  
 *型指定子*  
  
 *関数指定子*  
  
 [friend](friend-cpp.md)  
 
 [typedef](aliases-and-typedefs-cpp.md) `(` *拡張修飾子宣言 seq* `)`  

 [_ _declspec](declspec.md) `(` *拡張修飾子宣言 seq* `)`  
  
## <a name="remarks"></a>Remarks  
 *子*宣言の一部が最も長いシーケンスの*子*ポインターを含まない型名を示すや参照修飾子を使用できます。 宣言の残りの部分は、*宣言子*、導入された名前が含まれます。  
  
 次の表は、次の 4 つの宣言を一覧表示し、各宣言の一覧表示*宣言指定子*と*宣言子*コンポーネントとは別にします。  
  
|宣言|*宣言指定子*|`declarator`|  
|-----------------|------------------------|------------------|  
|`char *lpszAppName;`|**char**|`*lpszAppName`|  
|`typedef char * LPSTR;`|**char**|`*LPSTR`|  
|`const int func1();`|**const int**|`func1`|  
|`volatile void *pvvObj;`|**揮発性 void**|`*pvvObj`|  
  
 **署名**、**符号なし**、**長い**、および**短い**意味すべて**int**、 **typedef**名前を次のメンバーであるこれらのキーワードのいずれかが実行*宣言リスト、* のではありません*子*します。  
  
> [!NOTE]
>  名前は再宣言できるため、その解釈は、現在のスコープ内の最新の宣言に従います。 再宣言の名前の解釈方法、コンパイラによって特にに影響する可能性**typedef**名。  
  
## <a name="see-also"></a>関連項目  
 [宣言と定義](declarations-and-definitions-cpp.md)
