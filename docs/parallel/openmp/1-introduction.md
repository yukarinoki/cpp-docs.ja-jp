---
title: 1. 概要 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: c42e72bc-0e31-4b1c-b670-cd82673c0c5a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4ce963d312d145e26567a5902f32e45735eb1d89
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46438419"
---
# <a name="1-introduction"></a>1.はじめに

このドキュメントでは、コンパイラ ディレクティブ、ライブラリ関数、および C および C++ プログラムでの共有メモリの並列処理の指定に使用できる環境変数のコレクションを指定します。 このドキュメントで説明されている機能と総称、 *OpenMP C と C++ アプリケーション プログラム インターフェイス (API)* します。 この仕様の目的では、並列プログラミング モデルを提供するにより、さまざまなベンダーからの共有メモリ アーキテクチャ間で移植できるプログラムです。 OpenMP C と C++ の API は、多数のベンダーからのコンパイラでサポートされます。 OpenMP の詳細についてを含む、 *OpenMP Fortran アプリケーション プログラミング インターフェイス*、次の web サイトにあります。

[http://www.openmp.org](http://www.openmp.org)

ディレクティブ、ライブラリ関数、およびこのドキュメントで定義されている環境変数により、ユーザーを作成および移植性を確保しながら、並列プログラムを管理します。 ディレクティブは、C の拡張し、複数の data (SPMD) コンス トラクター、work-sharing コンス トラクター、および同期の構成体は、1 つのプログラムを使用する C++ のシーケンシャルなプログラミング モデル、共有とのデータをプライベート化のサポートを提供します。 OpenMP C および C++ API をサポートするコンパイラをアクティブ化し、すべての OpenMP コンパイラ ディレクティブの解釈は、コンパイラにコマンド ライン オプションが含まれます。