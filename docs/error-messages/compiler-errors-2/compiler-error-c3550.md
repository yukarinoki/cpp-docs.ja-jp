---
title: コンパイラ エラー C3550
ms.date: 11/04/2016
f1_keywords:
- C3550
helpviewer_keywords:
- C3550
ms.assetid: 9f2d5ffc-e429-41a1-89e3-7acc4fd47e14
ms.openlocfilehash: 17c90aa68b29c9490deb8d49895162e8a6bdefec
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80200773"
---
# <a name="compiler-error-c3550"></a>コンパイラ エラー C3550

このコンテキストでは単純な 'decltype(auto)' のみが許可されます

`decltype(auto)` を関数の戻り値の型のプレースホルダーとして使用する場合は、単独で使用する必要があります。 ポインターの宣言 (`decltype(auto*)`)、参照の宣言 (`decltype(auto&)`)、またはその他の修飾の一部として使用することはできません。

## <a name="see-also"></a>参照

[auto](../../cpp/auto-cpp.md)
