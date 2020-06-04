---
title: 致命的なエラー C1853
ms.date: 11/04/2016
f1_keywords:
- C1853
helpviewer_keywords:
- C1853
ms.assetid: ceb9b4a5-92bf-4573-8a9f-3109cc7743ce
ms.openlocfilehash: 056db975fecef4e101dbbba7e2084236489498c7
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80202866"
---
# <a name="fatal-error-c1853"></a>致命的なエラー C1853

> '*filename*' プリコンパイル済みヘッダーファイルが以前のバージョンのコンパイラからのものであるかC++ 、プリコンパイル済みヘッダーが C から使用されています (またはその逆)。

考えられる原因:

- プリコンパイル済みヘッダーは、以前のバージョンのコンパイラでコンパイルされました。 現在のコンパイラでヘッダーを再コンパイルしてみてください。

- プリコンパイル済みヘッダー C++はで、c から使用しています。 [/tc](../../build/reference/tc-tp-tc-tp-specify-source-file-type.md)コンパイラオプションのいずれかを指定するか、ソースファイルのサフィックスを "c" に変更して、c で使用できるようにヘッダーを再コンパイルしてみてください。 詳細については、「[コードをプリコンパイルする2つの選択肢](../../build/creating-precompiled-header-files.md#two-choices-for-precompiling-code)」を参照してください。
