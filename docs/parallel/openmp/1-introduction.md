---
title: 1. 概要 |Microsoft ドキュメント
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
ms.openlocfilehash: 883af9cb48a0fb13dbb9a758d6f8174096d4c0c3
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
---
# <a name="1-introduction"></a>1.はじめに
このドキュメントでは、コンパイラ ディレクティブ、ライブラリ関数、および C および C++ プログラムで共有メモリの並列処理を指定するために使用する環境変数のコレクションを指定します。 このドキュメントで説明されている機能と総称、 *OpenMP C と C++ アプリケーション プログラム インターフェイス (API)* です。 この仕様の目的は、並列プログラミング モデルを提供するさまざまなベンダーから共有メモリ アーキテクチャ間で移植できるプログラムです。 OpenMP C と C++ API は、多くのベンダーからのコンパイラでサポートされます。 詳細については、OpenMP など、 *OpenMP Fortran アプリケーション プログラム インターフェイス*、次の web サイトで見つかんだことができます。  
  
 [http://www.openmp.org](http://www.openmp.org)  
  
 ディレクティブ、ライブラリ関数、およびこのドキュメントで定義されている環境変数、ユーザーが作成および移植性を確保しながら並列プログラムを管理します。 ディレクティブは、C の拡張し複数の data (SPMD) コンス トラクターの work-sharing コンス トラクター、および同期構造は、1 つのプログラムを使用するシーケンシャルの C++ プログラミング モデルし、の共有とプライベート データのサポートを提供します。 OpenMP C および C++ API をサポートするコンパイラを有効にし、すべての OpenMP コンパイラ ディレクティブの解釈は、コンパイラにコマンド ライン オプションが含まれます。