---
description: 詳細については、「コンパイラエラー C2692」を参照してください。
title: コンパイラエラー C2692
ms.date: 11/04/2016
f1_keywords:
- C2692
helpviewer_keywords:
- C2692
ms.assetid: 02ade3b4-b757-448b-b065-d7d71bc3f441
ms.openlocfilehash: 5a9666bf437d65c54d0cb8c460054b2b3ebd0b55
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97326685"
---
# <a name="compiler-error-c2692"></a>コンパイラエラー C2692

' function_name ': '/clr ' オプションを指定した C コンパイラでは、完全なプロトタイプ関数が必要です

.NET マネージコードをコンパイルする場合、C コンパイラでは ANSI 関数宣言が必要です。 また、関数がパラメーターを受け取らない場合は、 **`void`** パラメーターの型として明示的に宣言する必要があります。
