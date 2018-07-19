---
title: リモート アーカイブ プロパティ (C++ Linux) | Microsoft Docs
ms.custom: ''
ms.date: 9/26/2017
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: Linux
ms.topic: conceptual
ms.assetid: 5ee1e44c-8337-4c3a-b2f3-35e4be954f9f
author: mikeblome
ms.author: mblome
f1_keywords: []
ms.workload:
- cplusplus
- linux
ms.openlocfilehash: 004e015b7e5ad8a99b3bea2bf21b7b598f2fedbd
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33328654"
---
# <a name="remote-archive-properties-c-linux"></a>リモート アーカイブ プロパティ (C++ Linux)

プロパティ | 説明
--- | ---
アーカイブ インデックスの作成 | アーカイブ インデックス (cf. ranlib) を作成します。  これにより、リンク処理を高速化し、ライブラリ内の依存関係を削減できます。
シン アーカイブの作成 | シン アーカイブを作成します。  シン アーカイブにはオブジェクトの相対パスが含まれます。相対パスを含めることは、オブジェクトを組み込むことの代わりになります。  シンと標準を切り替えるには、既存のライブラリを削除する必要があります。
作成時の警告なし | ライブラリが作成されても警告を出しません。
タイムスタンプの切り捨て | タイムスタンプおよび UID/GID に 0 を使用します。
著作権情報の非表示 | バージョン番号を表示しません。
詳細 | 詳細
その他のオプション | その他のオプションです。
出力ファイル | /OUT オプションを使用すると、lib によって作成されるプログラムの既定の名前と場所がオーバーライドされます。
アーカイブ処理 | スタティック オブジェクトのリンク中に起動するプログラムか、またはリモート システム上のアーカイブ処理へのパスを指定します。
アーカイブ処理のタイムアウト | リモート アーカイブ処理のタイムアウト (ミリ秒)。
出力データをコピーします | リモート システムからローカル コンピューターにビルドの出力ファイルをコピーするかどうかを指定します。
