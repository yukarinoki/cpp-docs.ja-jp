---
title: リソース コンパイラの致命的なエラー RC1052
ms.date: 11/04/2016
f1_keywords:
- RC1052
helpviewer_keywords:
- RC1052
ms.assetid: 59803673-492b-44fa-80fa-df93b8aaf9fb
ms.openlocfilehash: ad0fe23b20870610c5979d6ad85fce55b4e506d3
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80182557"
---
# <a name="resource-compiler-fatal-error-rc1052"></a>リソース コンパイラの致命的なエラー RC1052

コンパイラの制限: #if または #ifdef ブロックの入れ子のレベルが深すぎます。

プログラムが `#if` と `#ifdef` のディレクティブに許容される最大の入れ子レベルを超えました。

このエラーは、これらのプリプロセッサ ディレクティブを使用するインクルード ファイルによって発生することがあります。

この問題を解決するには、リソース ファイル内の、入れ子になっている `#if` と `#ifdef` ディレクティブの数を減らします。 リソース ファイルに含まれているヘッダー ファイルによって問題が発生している場合は、ヘッダー ファイル内の、入れ子になった `#if` と `#ifdef`ディレクティブの数を減らします。 これができない場合は、既存のヘッダー ファイルに対してプリプロセッサを実行して、新しいヘッダー ファイルを作成し、リソース ファイルに含めることを検討してください。 詳細については、「 [/p (ファイルに前処理する)](../../build/reference/p-preprocess-to-a-file.md)コンパイラオプション」を参照してください。
