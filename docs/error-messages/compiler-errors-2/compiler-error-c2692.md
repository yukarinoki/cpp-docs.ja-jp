---
title: コンパイラエラー C2692
ms.date: 11/04/2016
f1_keywords:
- C2692
helpviewer_keywords:
- C2692
ms.assetid: 02ade3b4-b757-448b-b065-d7d71bc3f441
ms.openlocfilehash: 7ce57cd50e9ec83cf80ec64e14f49eb9714f9208
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80177093"
---
# <a name="compiler-error-c2692"></a>コンパイラエラー C2692

' function_name ': '/clr ' オプションを指定した C コンパイラでは、完全なプロトタイプ関数が必要です

.NET マネージコードをコンパイルする場合、C コンパイラでは ANSI 関数宣言が必要です。 また、関数がパラメーターを受け取らない場合は、パラメーターの型として `void` を明示的に宣言する必要があります。
