---
description: '詳細情報: 致命的なエラー C1853'
title: 致命的なエラー C1853
ms.date: 11/04/2016
f1_keywords:
- C1853
helpviewer_keywords:
- C1853
ms.assetid: ceb9b4a5-92bf-4573-8a9f-3109cc7743ce
ms.openlocfilehash: 60c8e254e9bd36f52bddb4d6dce56c987b6c31e1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97276232"
---
# <a name="fatal-error-c1853"></a>致命的なエラー C1853

> '*filename*' プリコンパイル済みヘッダーファイルは、以前のバージョンのコンパイラからのものです。また、C++ のプリコンパイル済みヘッダーファイルを c で使用しています (またはその逆)。

次の原因が考えられます。

- プリコンパイル済みヘッダーは、以前のバージョンのコンパイラでコンパイルされました。 現在のコンパイラでヘッダーを再コンパイルしてみてください。

- プリコンパイル済みヘッダーは C++ で、C から使用しています。 [/tc](../../build/reference/tc-tp-tc-tp-specify-source-file-type.md) コンパイラオプションのいずれかを指定するか、ソースファイルのサフィックスを "c" に変更して、c で使用できるようにヘッダーを再コンパイルしてみてください。 詳細については、「 [コードをプリコンパイルする2つの選択肢](../../build/creating-precompiled-header-files.md#two-choices-for-precompiling-code)」を参照してください。
