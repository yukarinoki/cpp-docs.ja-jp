---
title: リソース コンパイラの警告 RC4093 |Microsoft ドキュメント
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
ms.openlocfilehash: e9cca3c2a139e1109746f3a690cfb3f31509a9fe
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33322433"
---
# <a name="resource-compiler-warning-rc4093"></a>リソース コンパイラの警告 RC4093
文字定数の非アクティブなコードでエスケープされていない改行  
  
 定数式、 `#if`、 `#elif`、 **#ifdef**、または **#ifndef**プリプロセッサ ディレクティブが 0 の場合、コードを作成するために評価が非アクティブに従います。 その使用頻度の低いコード内では、改行文字は、一重引用符または二重引用符のセット内で表示されます。  
  
 [次へ] のダブル クォーテーション マークまでのすべてのテキストは、文字定数内にあると見なされます。