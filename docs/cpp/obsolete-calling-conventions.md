---
description: '詳細情報: 互換性のために残されている呼び出し規約'
title: 廃止された呼び出し規約
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
ms.openlocfilehash: 0dfbb34215ba79b54d01ce12fe4d543dbe1d6859
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97146043"
---
# <a name="obsolete-calling-conventions"></a>廃止された呼び出し規約

**Microsoft 固有の仕様**

**__Pascal**、 **__fortran**、および **__syscall** の呼び出し規約はサポートされなくなりました。 サポートされる呼び出し規則および適切なリンカー オプションの 1 つを使用して、それらの機能をエミュレートできます。

\<windows.h> では、WINAPI マクロがサポートされるようになりました。これは、ターゲットの適切な呼び出し規約に変換されます。 以前に PASCAL または **__far \_ _pascal** を使用していた場合は、を使用します。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[引数の渡し規則と名前付け規則](../cpp/argument-passing-and-naming-conventions.md)
