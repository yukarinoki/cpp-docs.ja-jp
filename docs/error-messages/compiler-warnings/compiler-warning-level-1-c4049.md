---
title: コンパイラの警告 (レベル 1) C4049
ms.date: 11/04/2016
f1_keywords:
- C4049
helpviewer_keywords:
- C4049
ms.assetid: d11c1870-bcfc-4d71-8945-b87ec6ec3514
ms.openlocfilehash: 214ccae5d9835bc4a3b66bbbe1cd5ded4bc651cb
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80164145"
---
# <a name="compiler-warning-level-1-c4049"></a>コンパイラの警告 (レベル 1) C4049

コンパイラの制限: 行番号の出力を終了します。

ファイルのソース行が 16777215 (2<sup>24</sup>-1) を超えています。 コンパイラは16777215で番号付けを停止します。

16777215行目以降のコードの場合:

- イメージには、行番号のデバッグ情報は含まれません。

- 一部の診断は、正しくない行番号で報告される場合があります。

- .asm の一覧 (/fa) に無効な行番号が含まれている可能性があります。
