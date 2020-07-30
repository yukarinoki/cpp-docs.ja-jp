---
title: コンパイラエラー C2692
ms.date: 11/04/2016
f1_keywords:
- C2692
helpviewer_keywords:
- C2692
ms.assetid: 02ade3b4-b757-448b-b065-d7d71bc3f441
ms.openlocfilehash: a82ee0bead9e4e7a92c16df89eee86288f562de9
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87216103"
---
# <a name="compiler-error-c2692"></a>コンパイラエラー C2692

' function_name ': '/clr ' オプションを指定した C コンパイラでは、完全なプロトタイプ関数が必要です

.NET マネージコードをコンパイルする場合、C コンパイラでは ANSI 関数宣言が必要です。 また、関数がパラメーターを受け取らない場合は、 **`void`** パラメーターの型として明示的に宣言する必要があります。
