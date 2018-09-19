---
title: コンパイラ エラー C2696 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2696
dev_langs:
- C++
helpviewer_keywords:
- C2696
ms.assetid: 6c6eb7df-1230-4346-9a73-abf14c20785d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e6e76b0c11d329c734b0609c540aca4315c7ed9f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46108743"
---
# <a name="compiler-error-c2696"></a>コンパイラ エラー C2696

管理対象の型 'type' の一時オブジェクトを作成することはできません。

参照`const`アンマネージ プログラムが、コンパイラはコンス トラクターを呼び出すし、スタック上に一時オブジェクトを作成します。 ただし、マネージ クラスはスタックで作成できません。

C2696 は古い形式のコンパイラ オプションを使用して到達のみ **/clr:oldSyntax**します。
