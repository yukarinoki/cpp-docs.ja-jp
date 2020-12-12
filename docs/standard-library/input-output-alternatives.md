---
description: 詳細については、「入力/出力の代替手段」を参照してください。
title: Input-Output 代替手段
ms.date: 05/07/2019
helpviewer_keywords:
- I/O [C++], alternatives
ms.assetid: 9f8401c7-d90d-4285-8918-63573df74a80
ms.openlocfilehash: a6df022dd38bc23eaaaad49620067aca408b2df2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97324003"
---
# <a name="inputoutput-alternatives"></a>入出力の代替手段

Microsoft C++ コンパイラでは、i/o プログラミングにいくつかの代替手段が用意されています。

- C ランタイム ライブラリの直接的なバッファーされない入出力。

- ANSI C ランタイム ライブラリのストリーム入出力。

- コンソールおよびポートの直接入出力。

- Microsoft Foundation Class ライブラリ。

- Microsoft C++ 標準ライブラリ。

iostream クラスは、バッファーされた書式設定テキストの入出力に役立ちます。 C++ プログラミング インターフェイスが必要であり、Microsoft Foundation Class (MFC) ライブラリを使用しない場合のバッファーされていない入出力またはバイナリ入出力にも役立ちます。 iostream クラスは、C ランタイム関数のオブジェクト指向の入出力の代替手段です。

iostream クラスは、Microsoft Windows オペレーティング システムで使用できます。 文字列とファイルのストリームは制限なしで動作しますが、文字モード ストリーム オブジェクト `cin`、`cout`、`cerr`、および `clog` には Windows グラフィカル ユーザー インターフェイスとの一貫性がありません。 また、Windows 環境と直接やり取りするカスタム ストリーム クラスを派生させることもできます。

## <a name="see-also"></a>関連項目

[ストリームとは](../standard-library/what-a-stream-is.md)
