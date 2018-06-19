---
title: 指定子の使用 |Microsoft ドキュメント
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
ms.openlocfilehash: f2888f8a75e9b7addd2b8f195ffbf875c2b7ae1a
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32422327"
---
# <a name="specifiers"></a>指定子
このトピックの内容について説明します、*子*の (宣言指定子) コンポーネント、[宣言](declarations-and-definitions-cpp.md)です。  
  
 次のプレースホルダーと言語キーワードは宣言指定子です。  
  
 *ストレージ クラス指定子*  
  
 *型指定子*  
  
 *関数指定子*  
  
 [friend](../cpp/friend-cpp.md)  
  
 [typedef](http://msdn.microsoft.com/en-us/cc96cf26-ba93-4179-951e-695d1f5fdcf1)  
  
 [_ _declspec](../cpp/declspec.md) `(` *拡張修飾子 decl seq* `)`  
  
## <a name="remarks"></a>コメント  
 *子*宣言の一部が最も長いシーケンスの*子*という意味では、ポインターを含まない型名、または参照修飾子を実行することができます。 宣言の残りの部分は、*宣言子*、導入された名前が含まれます。  
  
 次の表の 4 つの宣言を一覧表示し、各宣言の一覧表示*宣言指定子*と*宣言子*コンポーネントとは別にします。  
  
|宣言|*宣言指定子*|`declarator`|  
|-----------------|------------------------|------------------|  
|`char *lpszAppName;`|`char`|`*lpszAppName`|  
|`typedef char * LPSTR;`|`char`|`*LPSTR`|  
|`const int func1();`|`const int`|`func1`|  
|`volatile void *pvvObj;`|`volatile void`|`*pvvObj`|  
  
 `signed`、 `unsigned`、 `long`、および`short`意味すべて`int`、`typedef`名前を次のメンバーであるこれらのキーワードのいずれかが実行*宣言子リスト、* のではありません*子*です。  
  
> [!NOTE]
>  名前は再宣言できるため、その解釈は、現在のスコープ内の最新の宣言に従います。 再宣言は、名前 (特に `typedef` 名) がコンパイラによってどのように解釈されるかに影響を与える可能性があります。  
  
## <a name="see-also"></a>関連項目  
 [宣言と定義](declarations-and-definitions-cpp.md)