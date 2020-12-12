---
description: 詳細については、「リソースコンパイラエラー RC2001」を参照してください。
title: リソース コンパイラ エラー RC2001
ms.date: 11/04/2016
f1_keywords:
- RC2001
helpviewer_keywords:
- RC2001
ms.assetid: 92bfb4c0-1879-4606-bb9f-ef7368707b4a
ms.openlocfilehash: 101ebb260bcfd24fb74368ca66e1e9d318418367
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97206345"
---
# <a name="resource-compiler-error-rc2001"></a>リソース コンパイラ エラー RC2001

定数の改行

文字列定数は、円記号 () を付けずに2行目に続きました **\\** 。または、二重引用符 (**"**) も閉じていません。

ソースファイル内の2行にある文字列定数を分割するには、次のいずれかの操作を行います。

- 行連結文字 (円記号) を使用して最初の行を終了します。

- 最初の行で二重引用符で囲まれた文字列を閉じ、次の行の文字列を別の引用符で開きます。

文字列定数に改行文字を埋め込むためのエスケープシーケンスである \n を使用して最初の行を終了するのは十分ではありません。
