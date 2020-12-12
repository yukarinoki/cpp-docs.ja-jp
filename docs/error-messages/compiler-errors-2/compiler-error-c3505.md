---
description: 詳細については、「コンパイラエラー C3505」を参照してください。
title: コンパイラ エラー C3505
ms.date: 11/04/2016
f1_keywords:
- C3505
helpviewer_keywords:
- C3505
ms.assetid: ed73c99e-93a1-4f3a-bac7-ba7ed5d836e4
ms.openlocfilehash: 10727b04ce587eb56872440ad7d46dd544eb0642
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97113114"
---
# <a name="compiler-error-c3505"></a>コンパイラ エラー C3505

> タイプライブラリ '*guid*' を読み込めません

コンパイラは WOW64 で実行されていて、32ビットレジストリハイブからの読み取りのみが可能であるため、64ビットコンピューターで32ビット、x86 でホストされているクロス64コンパイラを実行している場合、C3505 が発生する可能性があります。

このエラーを解決するには、インポートしようとしているタイプライブラリの32ビットバージョンと64ビットバージョンの両方をビルドし、両方を登録します。  または、ネイティブの64ビットコンパイラを使用することもできます。そのためには、IDE で **VC + + ディレクトリ** プロパティを変更して64ビットコンパイラをポイントする必要があります。

詳細については、次のトピックを参照してください。

- [方法: 64 ビットの Visual C++ ツールセットをコマンド ラインから有効にする](../../build/how-to-enable-a-64-bit-visual-cpp-toolset-on-the-command-line.md)

- [方法: Visual C++ プロジェクトを 64 ビット、x64 プラットフォーム用に設定する](../../build/how-to-configure-visual-cpp-projects-to-target-64-bit-platforms.md)
