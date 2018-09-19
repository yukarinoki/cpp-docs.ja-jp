---
title: リソース コンパイラの警告 RC4093 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- RC4093
dev_langs:
- C++
helpviewer_keywords:
- RC4093
ms.assetid: 3c61b4a4-b418-465b-a4fd-cb1ff0adb8dd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9b1ca04b17ebdb9d48bc94032482caf48ad4aa00
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46111564"
---
# <a name="resource-compiler-warning-rc4093"></a>リソース コンパイラの警告 RC4093

アクティブでないコード内の文字定数のエスケープ解除された改行

定数式、 `#if`、 `#elif`、 **#ifdef**、または **#ifndef**プリプロセッサ ディレクティブが 0 の場合、コードを作成するために評価が非アクティブに従います。 改行文字は、非アクティブなコード内で単一引用符または二重引用符のセット内で表示されます。

[次へ] の二重引用符までのすべてのテキストは、文字定数内にあると見なされていました。