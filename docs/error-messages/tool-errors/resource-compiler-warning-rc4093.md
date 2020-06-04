---
title: リソース コンパイラの警告 RC4093
ms.date: 11/04/2016
f1_keywords:
- RC4093
helpviewer_keywords:
- RC4093
ms.assetid: 3c61b4a4-b418-465b-a4fd-cb1ff0adb8dd
ms.openlocfilehash: 29d24f1e380f5c531e170e5dc23cf5c77eefb874
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80182293"
---
# <a name="resource-compiler-warning-rc4093"></a>リソース コンパイラの警告 RC4093

アクティブでないコード内の文字定数でエスケープ解除される改行

`#if`、`#elif`、 **#ifdef**、または **#ifndef**プリプロセッサディレクティブの定数式が0に評価され、コードが非アクティブになります。 この非アクティブコード内では、改行文字が単一引用符または二重引用符のセット内に表示されます。

次の二重引用符までのすべてのテキストは、文字定数内にあると見なされます。
