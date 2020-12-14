---
description: '詳細情報: 致命的なエラー C1854'
title: 致命的なエラー C1854
ms.date: 11/04/2016
f1_keywords:
- C1854
helpviewer_keywords:
- C1854
ms.assetid: 8c21a9cc-1737-475c-9e57-8725cd8937c1
ms.openlocfilehash: 1c08db55089853545afa511213fc164c978bd4ff
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97276206"
---
# <a name="fatal-error-c1854"></a>致命的なエラー C1854

> オブジェクトファイルでプリコンパイル済みヘッダーの作成中に形成された情報を上書きできません: '*filename*'

同じファイルに対して [ [/yc (プリコンパイル済みヘッダーファイルの作成)](../../build/reference/yc-create-precompiled-header-file.md) ] オプションを指定した後、[ [/Yu (プリコンパイル済みヘッダーファイルを使用)](../../build/reference/yu-use-precompiled-header-file.md) ] オプションを指定しました。

この問題を解決するには、通常、 **/yc** オプションを使用してコンパイルするプロジェクト内のファイルを1つだけ設定し、 **/yu** オプションを使用して他のすべてのファイルをコンパイルするように設定します。 **/Yc** オプションの使用方法、および VISUAL Studio IDE での設定方法の詳細については、「 [/Yc (プリコンパイル済みヘッダーファイルの作成)](../../build/reference/yc-create-precompiled-header-file.md)」を参照してください。 プリコンパイル済みヘッダーの使用方法の詳細については、「 [プリコンパイル済みヘッダーファイルの作成](../../build/creating-precompiled-header-files.md)」を参照してください。
