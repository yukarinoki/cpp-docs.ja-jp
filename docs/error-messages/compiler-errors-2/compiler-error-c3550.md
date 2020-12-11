---
description: 詳細については、「コンパイラエラー C3550」を参照してください。
title: コンパイラ エラー C3550
ms.date: 11/04/2016
f1_keywords:
- C3550
helpviewer_keywords:
- C3550
ms.assetid: 9f2d5ffc-e429-41a1-89e3-7acc4fd47e14
ms.openlocfilehash: 4cb459e3f8e7fdd0dbb00c1d4dfaa3c3c6b1eb71
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97112415"
---
# <a name="compiler-error-c3550"></a>コンパイラ エラー C3550

このコンテキストでは単純な 'decltype(auto)' のみが許可されます

`decltype(auto)` を関数の戻り値の型のプレースホルダーとして使用する場合は、単独で使用する必要があります。 ポインターの宣言 (`decltype(auto*)`)、参照の宣言 (`decltype(auto&)`)、またはその他の修飾の一部として使用することはできません。

## <a name="see-also"></a>関連項目

[auto](../../cpp/auto-cpp.md)
