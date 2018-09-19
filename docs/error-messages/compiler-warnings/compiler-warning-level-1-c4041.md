---
title: コンパイラの警告 (レベル 1) C4041 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4041
dev_langs:
- C++
helpviewer_keywords:
- C4041
ms.assetid: 107ee9fd-4b88-4f22-a18f-a20726831095
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9ff2c8066557e420ecd7de561d7731b7be733315
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46085785"
---
# <a name="compiler-warning-level-1-c4041"></a>コンパイラの警告 (レベル 1) C4041

コンパイラの制限 : ブラウザーの出力を中止します。

ブラウザー情報がコンパイラの制限を超えました。

この警告は、 [/FR](../../build/reference/fr-fr-create-dot-sbr-file.md) (ローカル変数を含めたブラウザー情報) でコンパイルすると発生することがあります。

### <a name="to-fix-by-using-the-following-possible-solutions"></a>修復の可能性がある解決策

1. /Fr (ローカル変数を含まないブラウザー情報) でコンパイルします。

1. ブラウザーの出力 (/FR や /Fr なしのコンパイル) を無効にします。