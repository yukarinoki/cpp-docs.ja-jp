---
description: '詳細情報: 致命的なエラー C1047'
title: 致命的なエラー C1047
ms.date: 02/17/2021
f1_keywords:
- C1047
helpviewer_keywords:
- C1047
ms.openlocfilehash: f22d7c7591e2c2c477d09f1637641cc351eeafb5
ms.sourcegitcommit: 5efc34c2b98d4d0d3e41aec38b213f062c19d078
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2021
ms.locfileid: "101844482"
---
# <a name="fatal-error-c1047"></a>致命的なエラー C1047

> オブジェクトまたはライブラリファイル '*filename*' は、他のオブジェクトよりも古いコンパイラで作成されました。古いオブジェクトとライブラリを再構築する

このエラーは、新しいバージョンのコンパイラを使用してプロジェクトをビルドし、既存のオブジェクトファイルまたはライブラリのクリーンリビルドを実行しない場合に発生する可能性があります。

## <a name="remarks"></a>解説

C1047 は、またはを使用してビルドされたオブジェクトファイルまたはライブラリが **`/GL`** **`/LTCG`** 、異なるバージョンの Visual Studio C/c + + コンパイラツールセットにリンクしている場合に発生します。 たとえば、 **`/LTCG`** Visual studio 2019 バージョン16.7 を使用してビルドされたライブラリを、Visual studio 2019 バージョン16.8 を使用してビルドされたアプリにリンクすることはできません。 オブジェクトとライブラリをコンパイルするために使用されるツールセットのメジャーおよびマイナーの更新番号は、完全に一致している必要があります。

C1047 を解決するには、同じバージョンのツールセットを使用して、すべてのオブジェクトファイルまたはライブラリをリビルドします。

## <a name="see-also"></a>関連項目

[`/GL` (プログラム全体の最適化)](../../build/reference/gl-whole-program-optimization.md)\
[`/LTCG` (リンク時のコード生成)](../../build/reference/ltcg-link-time-code-generation.md)\
[2015 と 2019 間の C++ のバイナリの互換性](../../porting/binary-compat-2015-2017.md)
