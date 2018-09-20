---
title: 1.4 コンプライアンス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 662ad260-b9a1-43b7-b269-ef6ff0714e05
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1a332d8fb5de172c363c6f9c1bebba65d6fa0ff8
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46381817"
---
# <a name="14-compliance"></a>1.4 準拠

OpenMP C と C++ の API の実装は*OpenMP 準拠*は、付録 C A、B、D、E、および F とかどうかを認識し、章 1、2、3、4、レイアウトとは、この仕様は、のすべての要素のセマンティクスを保持情報は、のみを目的し、仕様の一部ではないです。 API のサブセットのみを含む実装は、OpenMP 準拠ではありません。

OpenMP C および C++ API は、実装でサポートされているベース言語の拡張機能です。 基本言語をサポートしていない言語コンストラクトまたは表示される拡張機能をこのドキュメントの場合、サポートするように、OpenMP の実装は必要ありません。

すべての C および C++ の標準ライブラリ関数と組み込み関数 (つまり、コンパイラが特定のナレッジには、関数) スレッド セーフである必要があります。 同期されていない使用の並列領域内の別のスレッドでスレッド セーフな関数のでは、未定義の動作は発生しません。 ただし、動作できない serial リージョンと同じです。 (ランダムな番号の生成関数は、例を示します)。

OpenMP C と C++ API では、特定の動作は、ことを指定します*実装で定義されます。* OpenMP に準拠した実装は、定義し、このような場合は、その動作を文書化する必要があります。 参照してください[付録 E](../../parallel/openmp/e-implementation-defined-behaviors-in-openmp-c-cpp.md)、実装定義の動作の一覧については、97 ページします。