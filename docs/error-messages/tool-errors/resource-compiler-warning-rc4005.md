---
title: リソース コンパイラの警告 RC4005
ms.date: 11/04/2016
f1_keywords:
- RC4005
helpviewer_keywords:
- RC4005
ms.assetid: 71f03b4a-c9a9-415d-920f-bf2e58507f93
ms.openlocfilehash: c428fefa90cceed6a8bc9b7f6e4b95ec2db5e039
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80182410"
---
# <a name="resource-compiler-warning-rc4005"></a>リソース コンパイラの警告 RC4005

' identifier ': マクロの再定義

識別子は2回定義されます。 コンパイラは2番目のマクロ定義を使用しました。

この警告は、コマンドラインでマクロを定義し、コードに `#define` ディレクティブを指定することによって発生することがあります。 また、インクルードファイルからインポートされたマクロによっても発生する可能性があります。

警告を除去するには、定義の1つを削除するか、2番目の定義の前に `#undef` ディレクティブを使用します。
