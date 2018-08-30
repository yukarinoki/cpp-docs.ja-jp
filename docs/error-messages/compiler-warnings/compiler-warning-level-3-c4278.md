---
title: コンパイラの警告 (レベル 3) C4278 |Microsoft Docs
ms.custom: ''
ms.date: 08/27/2018
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4278
dev_langs:
- C++
helpviewer_keywords:
- C4278
ms.assetid: 4b6053fb-df62-4c04-b6c8-c011759557b8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f63337de2e14b1cb0f9d854df962ab2aa9c8014e
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43205782"
---
# <a name="compiler-warning-level-3-c4278"></a>コンパイラの警告 (レベル 3) C4278

> '*識別子*': タイプ ライブラリ内の識別子'*tlb*' は既にマクロです 'rename' 修飾子。

使用する場合[#import](../../preprocessor/hash-import-directive-cpp.md)、インポートするタイプ ライブラリ内の識別子は、識別子を宣言しようとします。*識別子*します。 ただし、これは有効なシンボルでは既にします。

使用して、 `#import` **の名前を変更**属性をタイプ ライブラリ内のシンボルにエイリアスを割り当てます。