---
description: コンパイラの警告 (レベル 1) の詳細については、C4027 を参照してください。
title: コンパイラの警告 (レベル 1) C4027
ms.date: 12/16/2020
f1_keywords:
- C4027
helpviewer_keywords:
- C4027
ms.openlocfilehash: 1489ca32211854bcf1ef55d1a4ac806ab1611f43
ms.sourcegitcommit: 387ce22a3b0137f99cbb856a772b5a910c9eba99
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "97645177"
---
# <a name="compiler-warning-level-1-c4027"></a>コンパイラの警告 (レベル 1) C4027

> 関数はパラメーター リストなしで宣言されています。

関数宣言に仮引数がありませんでしたが、関数定義または呼び出しの実際のパラメーターに仮パラメーターがあります。

コンパイラは、パラメーターリストを使用せずに、関数名の古い C スタイルの事前宣言に対してを受け取りますが、警告を出します。 後でこの関数を呼び出すときに、コンパイラは、関数が関数定義または呼び出しで見つかった型の実際のパラメーターを受け取ることを前提としています。 関数定義のシグネチャに一致するように関数の宣言を変更することをお勧めします。
