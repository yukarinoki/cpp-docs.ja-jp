---
description: 詳細については、「リンカーツールの警告 LNK4206」を参照してください。
title: リンカー ツールの警告 LNK4206
ms.date: 12/05/2017
f1_keywords:
- LNK4206
helpviewer_keywords:
- LNK4206
ms.assetid: 6c108e33-00cf-4c5a-830d-d65d470930a7
ms.openlocfilehash: 40d7a8f18a835721ff747293696d0499c0a94ef3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97294146"
---
# <a name="linker-tools-warning-lnk4206"></a>リンカー ツールの警告 LNK4206

> プリコンパイル済みの型情報が見つかりません。'*filename*' はリンクされていないか、上書きされています。デバッグ情報がない場合と同様にオブジェクトをリンクしています

[/Yc](../../build/reference/yc-create-precompiled-header-file.md)を使用してコンパイルされた *filename* オブジェクトファイルが LINK コマンドで指定されていないか、上書きされました。

この警告の一般的なシナリオは、/Yc を使用してコンパイルされた .obj がライブラリ内にあり、コードからその .obj へのシンボル参照がない場合です。  その場合、リンカーは .obj ファイルを使用しない (または参照する) ことができません。  このような場合は、コードを再コンパイルし、 [/yu](../../build/reference/yu-use-precompiled-header-file.md)を使用してコンパイルされたオブジェクトに[/Yl](../../build/reference/yl-inject-pch-reference-for-debug-library.md)を使用する必要があります。
