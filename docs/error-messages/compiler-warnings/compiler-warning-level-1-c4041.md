---
description: '詳細情報: コンパイラの警告 (レベル 1) C4041'
title: コンパイラの警告 (レベル 1) C4041
ms.date: 11/04/2016
f1_keywords:
- C4041
helpviewer_keywords:
- C4041
ms.assetid: 107ee9fd-4b88-4f22-a18f-a20726831095
ms.openlocfilehash: d3473be35182f6c99541aa2a0fc79de79dee4a07
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97160715"
---
# <a name="compiler-warning-level-1-c4041"></a>コンパイラの警告 (レベル 1) C4041

コンパイラの制限 : ブラウザーの出力を中止します。

ブラウザー情報がコンパイラの制限を超えました。

この警告は、 [/FR](../../build/reference/fr-fr-create-dot-sbr-file.md) (ローカル変数を含めたブラウザー情報) でコンパイルすると発生することがあります。

### <a name="to-fix-by-using-the-following-possible-solutions"></a>以下の可能性がある解決策を使って修正するには

1. /Fr (ローカル変数を含まないブラウザー情報) でコンパイルします。

1. ブラウザーの出力 (/FR や /Fr なしのコンパイル) を無効にします。
