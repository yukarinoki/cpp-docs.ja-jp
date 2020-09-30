---
title: SBCS および MBCS データ型
description: Microsoft C ランタイムで1つの文字とマルチバイト文字を表す方法。
ms.topic: conceptual
ms.date: 04/11/2018
f1_keywords:
- MBCS
- SBCS
helpviewer_keywords:
- SBCS and MBCS data types
- data types [C], MBCS and SBCS
ms.assetid: 4c3ef9da-e397-48d4-800e-49dba36db171
ms.openlocfilehash: 27d32ffd079cdc82ab8a799df9d9ec778b546a3b
ms.sourcegitcommit: 9451db8480992017c46f9d2df23fb17b503bbe74
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/30/2020
ms.locfileid: "91590252"
---
# <a name="sbcs-and-mbcs-data-types"></a>SBCS および MBCS データ型

1つのマルチバイト文字またはマルチバイト文字の1バイトだけを処理する Microsoft MBCS ランタイムライブラリルーチンでは、引数を指定する必要が **`unsigned int`** あります (0x00 <= 文字値 <= 0xffff、0x00 <= バイト値 <= 0xff)。 マルチバイトのバイトまたは文字列コンテキスト内の文字を処理する MBCS ルーチンでは、マルチバイト文字列がポインターとして表現されることを想定して **`unsigned char`** います。

> [!CAUTION]
> マルチバイト文字の各バイトは8ビットで表すことができ **`char`** ます。 ただし、0x7F よりも大きい値を持つ型の SBCS または MBCS の1バイト文字 **`char`** は負になります。 このような文字が直接またはに変換されると、 **`int`** **`long`** 結果はコンパイラによって符号拡張されるため、予期しない結果が発生する可能性があります。

マルチバイト文字のバイトを8ビットとして表すことをお勧めし **`unsigned char`** ます。 または、負の結果を回避するには、型の1バイト文字を **`char`** またはに変換する前に、に変換し **`unsigned char`** **`int`** **`long`** ます。

一部の SBCS 文字列処理関数は (符号付き) **`char`** <strong>\*</strong> パラメーターを受け取るため、 **_MBCS**が定義されていると、型の不一致コンパイラの警告が発生します。 この警告を回避する方法を 3 つ、効率の順に次に示します。

1. TCHAR.H のタイプ セーフなインライン関数を使用します。 これが既定の動作です。

1. コマンド ラインで **_MB_MAP_DIRECT** を定義して、TCHAR.H の直接マクロを使用します。 この場合は、型を手作業で一致させる必要があります。 これは最速の方法ですが、タイプセーフではありません。

1. TCHAR.H のタイプ セーフな静的リンク ライブラリ関数を使用します。 この場合は、コマンド ラインで定数 **_NO_INLINING** を定義します。 これは、一番時間がかかりますが、一番タイプ セーフな方法です。

## <a name="see-also"></a>関連項目

[国際化](../c-runtime-library/internationalization.md)<br/>
[カテゴリ別ユニバーサル C ランタイム ルーチン](../c-runtime-library/run-time-routines-by-category.md)<br/>
