---
title: 入出力の代替手段
ms.date: 11/04/2016
helpviewer_keywords:
- I/O [C++], alternatives
ms.assetid: 9f8401c7-d90d-4285-8918-63573df74a80
ms.openlocfilehash: bc595b64c991ada8e958e71e13f8cb9d134adb8a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62404963"
---
# <a name="inputoutput-alternatives"></a>入出力の代替手段

Visual C++ には、入出力のプログラミングのいくつかの代替手段が用意されています。

- C ランタイム ライブラリの直接的なバッファーされない入出力。

- ANSI C ランタイム ライブラリのストリーム入出力。

- コンソールおよびポートの直接入出力。

- Microsoft Foundation Class ライブラリ。

- Microsoft C++ 標準ライブラリ。

iostream クラスは、バッファーされた書式設定テキストの入出力に役立ちます。 C++ プログラミング インターフェイスが必要であり、Microsoft Foundation Class (MFC) ライブラリを使用しない場合のバッファーされていない入出力またはバイナリ入出力にも役立ちます。 iostream クラスは、C ランタイム関数のオブジェクト指向の入出力の代替手段です。

iostream クラスは、Microsoft Windows オペレーティング システムで使用できます。 文字列とファイルのストリームは制限なしで動作しますが、文字モード ストリーム オブジェクト `cin`、`cout`、`cerr`、および `clog` には Windows グラフィカル ユーザー インターフェイスとの一貫性がありません。 また、Windows 環境と直接やり取りするカスタム ストリーム クラスを派生させることもできます。

## <a name="see-also"></a>関連項目

[ストリームとは何か](../standard-library/what-a-stream-is.md)<br/>
