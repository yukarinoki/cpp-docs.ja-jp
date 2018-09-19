---
title: コンパイラの警告 (レベル 1) C4049 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4049
dev_langs:
- C++
helpviewer_keywords:
- C4049
ms.assetid: d11c1870-bcfc-4d71-8945-b87ec6ec3514
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 68a89d02129e5e8fbedb0649fff0cfe3813304c5
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46053519"
---
# <a name="compiler-warning-level-1-c4049"></a>コンパイラの警告 (レベル 1) C4049

コンパイラの制限: 行番号の出力を終了しています

ファイルに含まれる複数の 16,777, 215 (2<sup>24</sup>-1) ソース行。 コンパイラは、連番が 16,777, 215 を停止します。

16,777, 215 の行の後のコード。

- イメージには、行番号のデバッグ情報はありません。

- いくつかの診断は、不適切な行番号で報告されること可能性があります。

- .asm 一覧 (/FAs) が正しくない行の番号があります。