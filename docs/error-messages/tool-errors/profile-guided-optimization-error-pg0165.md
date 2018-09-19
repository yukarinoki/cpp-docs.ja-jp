---
title: プロファイル ガイド付き最適化のエラー PG0165 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- PG0165
dev_langs:
- C++
helpviewer_keywords:
- PG0165
ms.assetid: e98122e7-ddee-4a2c-96b2-d232e4c65f3e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 332751a123bf7d6414c40b79870b5edf27a3d8a7
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46084212"
---
# <a name="profile-guided-optimization-error-pg0165"></a>ガイド付き最適化のプロファイルのエラー PG0165

'Filename.pgd' を読み込んでいます: ' PGD バージョンがサポートされていません (バージョンの不一致)' です。

PGD ファイルは、特定のコンパイラ ツールセットに固有です。 別のコンパイラを使用したものを使用しているときにこのエラーは生成*Filename*.pgd します。 このエラーは、このコンパイラ ツールセットからデータを使用できないことを示します*Filename*.pgd を現在のプログラムを最適化します。

この問題を解決するには、再生成*Filename*.pgd、現在のコンパイラ ツールセットを使用しています。