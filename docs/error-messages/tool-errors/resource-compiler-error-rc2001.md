---
title: リソース コンパイラ エラー RC2001
ms.date: 11/04/2016
f1_keywords:
- RC2001
helpviewer_keywords:
- RC2001
ms.assetid: 92bfb4c0-1879-4606-bb9f-ef7368707b4a
ms.openlocfilehash: 35042687b798b53857becdedba57861bd4f41a05
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80191725"
---
# <a name="resource-compiler-error-rc2001"></a>リソース コンパイラ エラー RC2001

定数の改行

文字列定数が、円記号 ( **\\** ) を使用しないか、二重引用符 ( **"** ) を閉じていない2行目で続行されました。

ソースファイル内の2行にある文字列定数を分割するには、次のいずれかの操作を行います。

- 行連結文字 (円記号) を使用して最初の行を終了します。

- 最初の行で二重引用符で囲まれた文字列を閉じ、次の行の文字列を別の引用符で開きます。

文字列定数に改行文字を埋め込むためのエスケープシーケンスである \n を使用して最初の行を終了するのは十分ではありません。
