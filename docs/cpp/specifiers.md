---
title: 指定子
ms.date: 11/04/2016
helpviewer_keywords:
- declaration specifiers
- declarations, specifiers
- specifiers, in declarations
ms.assetid: 8b14e844-9880-4571-8779-28c8efe44633
ms.openlocfilehash: aef967b26321f289cb8c7bd0402d7fe8f12b77b6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62330987"
---
# <a name="specifiers"></a>指定子

このトピックで説明します、*子*の (宣言指定子) コンポーネント、[宣言](declarations-and-definitions-cpp.md)します。

次のプレースホルダーと言語キーワードは宣言指定子です。

*storage-class-specifier*

*type-specifier*

*function-specifier*

[friend](friend-cpp.md)

[typedef](aliases-and-typedefs-cpp.md) `(` *extended-decl-modifier-seq* `)`

[__declspec](declspec.md) `(` *extended-decl-modifier-seq* `)`

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
