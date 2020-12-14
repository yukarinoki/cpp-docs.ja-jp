---
description: 詳細については、「リソースコンパイラの警告 RC4005」を参照してください。
title: リソース コンパイラの警告 RC4005
ms.date: 11/04/2016
f1_keywords:
- RC4005
helpviewer_keywords:
- RC4005
ms.assetid: 71f03b4a-c9a9-415d-920f-bf2e58507f93
ms.openlocfilehash: 138037e48356448550308abee8dc43cd06b9ac06
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97237128"
---
# <a name="resource-compiler-warning-rc4005"></a>リソース コンパイラの警告 RC4005

' identifier ': マクロの再定義

識別子は2回定義されます。 コンパイラは2番目のマクロ定義を使用しました。

この警告は、コマンドラインでマクロを定義し、ディレクティブを使用してコードに記述することによって発生することがあり `#define` ます。 また、インクルードファイルからインポートされたマクロによっても発生する可能性があります。

警告を除去するには、定義の1つを削除するか、 `#undef` 2 番目の定義の前にディレクティブを使用します。
