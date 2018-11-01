---
title: 廃止された呼び出し規則
ms.date: 11/04/2016
f1_keywords:
- __fortran
- __pascal
- __syscall
helpviewer_keywords:
- WINAPI [C++]
- __syscall keyword [C++]
- __pascal keyword [C++]
- __fortran keyword [C++]
- calling conventions, obsolete
ms.assetid: a91fc665-034a-48ce-b6bd-d27125f308a7
ms.openlocfilehash: 86c75c779158d9f191dd015410cf16c9ce25690d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50587994"
---
# <a name="obsolete-calling-conventions"></a>廃止された呼び出し規則

## <a name="microsoft-specific"></a>Microsoft 固有の仕様

**_ _Pascal**、 **_ _fortran**、および **_ _syscall**呼び出し規約はサポートされなくなりました。 サポートされる呼び出し規則および適切なリンカー オプションの 1 つを使用して、それらの機能をエミュレートできます。

\<windows.h > WINAPI マクロは、ターゲットの適切な呼び出し規約に変換するようになりました。 Pascal 形式を以前に使用される WINAPI を使用して、または **__far \__pascal**します。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[引数の渡し規則と名前付け規則](../cpp/argument-passing-and-naming-conventions.md)