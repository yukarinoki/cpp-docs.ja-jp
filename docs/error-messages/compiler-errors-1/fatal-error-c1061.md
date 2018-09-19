---
title: 致命的なエラー C1061 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1061
dev_langs:
- C++
helpviewer_keywords:
- C1061
ms.assetid: 9366c0bc-96e0-4967-aa7d-4ebf098de806
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 21ca27534aa23d0d81ec7fb191c336b35b18391a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46083276"
---
# <a name="fatal-error-c1061"></a>致命的なエラー C1061

コンパイラの制限 : プログラム内のブロックの入れ子のレベルが深すぎます。

コード内のブロックの入れ子レベルが、制限値 128 を超えています。 これは、32 ビットおよび 64 ビットのツール セットにおける、C と C++ の両方のコンパイラのハード リミットです。 入れ子レベルの数を増やすには、スコープまたはブロックを作成します。 たとえば、名前空間、ディレクティブの使用、プリプロセッサ拡張、テンプレート拡張、例外処理、ループ構造、および else-if 句のすべてが、コンパイラによって参照される入れ子レベルを増やすことができます。

このエラーを解決するには、コードをリファクタリングする必要があります。 いずれにしても、入れ子のレベルが深いコードはわかりにくく、推論も困難です。 コードをリファクタリングして入れ子レベルを減らすと、コードの品質が向上し、保守しやすくなる場合があります。 まず、入れ子のレベルが深いコードを、元のコンテキストから呼び出される関数に分割します。 そして、ブロック内のループまたはチェーンされた else-if 句の数を制限します。