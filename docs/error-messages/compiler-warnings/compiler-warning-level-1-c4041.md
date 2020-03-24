---
title: コンパイラの警告 (レベル 1) C4041
ms.date: 11/04/2016
f1_keywords:
- C4041
helpviewer_keywords:
- C4041
ms.assetid: 107ee9fd-4b88-4f22-a18f-a20726831095
ms.openlocfilehash: 14ea6d9cae3b490107b656153bb68815026971e1
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80164236"
---
# <a name="compiler-warning-level-1-c4041"></a>コンパイラの警告 (レベル 1) C4041

コンパイラの制限 : ブラウザーの出力を中止します。

ブラウザー情報がコンパイラの制限を超えました。

この警告は、 [/FR](../../build/reference/fr-fr-create-dot-sbr-file.md) (ローカル変数を含めたブラウザー情報) でコンパイルすると発生することがあります。

### <a name="to-fix-by-using-the-following-possible-solutions"></a>修復の可能性がある解決策

1. /Fr (ローカル変数を含まないブラウザー情報) でコンパイルします。

1. ブラウザーの出力 (/FR や /Fr なしのコンパイル) を無効にします。
