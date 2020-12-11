---
description: '詳細情報: コンパイラの警告 (レベル 1) C4049'
title: コンパイラの警告 (レベル 1) C4049
ms.date: 11/04/2016
f1_keywords:
- C4049
helpviewer_keywords:
- C4049
ms.assetid: d11c1870-bcfc-4d71-8945-b87ec6ec3514
ms.openlocfilehash: b6de6fd816be8925dab553ff4dc5a062300b42e5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97160572"
---
# <a name="compiler-warning-level-1-c4049"></a>コンパイラの警告 (レベル 1) C4049

コンパイラの制限: 行番号の出力を終了します。

ファイルのソース行が 16777215 (2<sup>24</sup>-1) を超えています。 コンパイラは16777215で番号付けを停止します。

16777215行目以降のコードの場合:

- イメージには、行番号のデバッグ情報は含まれません。

- 一部の診断は、正しくない行番号で報告される場合があります。

- .asm の一覧 (/fa) に無効な行番号が含まれている可能性があります。
