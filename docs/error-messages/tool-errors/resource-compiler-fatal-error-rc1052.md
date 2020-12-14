---
description: 詳細については、「リソースコンパイラの致命的なエラー RC1052」を参照してください。
title: リソース コンパイラの致命的なエラー RC1052
ms.date: 11/04/2016
f1_keywords:
- RC1052
helpviewer_keywords:
- RC1052
ms.assetid: 59803673-492b-44fa-80fa-df93b8aaf9fb
ms.openlocfilehash: 41ef30cfde7d463337b1747b3f6141866e39e3be
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97255081"
---
# <a name="resource-compiler-fatal-error-rc1052"></a>リソース コンパイラの致命的なエラー RC1052

コンパイラの制限: #if または #ifdef ブロックの入れ子のレベルが深すぎます。

プログラムが `#if` と `#ifdef` のディレクティブに許容される最大の入れ子レベルを超えました。

このエラーは、これらのプリプロセッサ ディレクティブを使用するインクルード ファイルによって発生することがあります。

この問題を解決するには、リソース ファイル内の、入れ子になっている `#if` と `#ifdef` ディレクティブの数を減らします。 リソース ファイルに含まれているヘッダー ファイルによって問題が発生している場合は、ヘッダー ファイル内の、入れ子になった `#if` と `#ifdef`ディレクティブの数を減らします。 これができない場合は、既存のヘッダー ファイルに対してプリプロセッサを実行して、新しいヘッダー ファイルを作成し、リソース ファイルに含めることを検討してください。 詳細については、「 [/p (ファイルに前処理する)](../../build/reference/p-preprocess-to-a-file.md) コンパイラオプション」を参照してください。
