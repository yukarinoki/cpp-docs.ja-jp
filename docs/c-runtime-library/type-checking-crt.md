---
description: '詳細情報: 型チェック (CRT)'
title: 型チェック (CRT)
ms.date: 11/04/2016
f1_keywords:
- c.types
helpviewer_keywords:
- checking type
- variable argument functions
- type checking
ms.assetid: 1ba7590b-d1c0-4636-b6a0-e231395abdad
ms.openlocfilehash: 9afb4146f7bbd08b35df20972345285bb353e4d3
ms.sourcegitcommit: 90c300b74f6556cb5d989802d2e80d79542f55e7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/09/2021
ms.locfileid: "102514227"
---
# <a name="type-checking-crt"></a>型チェック (CRT)

コンパイラは、制限付きの型チェックを行います。次のように、状況によって異なる数の引数をチェックします。

|関数呼び出し|型がチェックされる引数|
|-------------------|-----------------------------|
|`_cprintf_s`, `_cscanf_s`, `printf_s`, `scanf_s`|最初の引数 (書式設定文字列)|
|`fprintf_s`, `fscanf_s`, `sprintf_s`, `sscanf_s`|最初の 2 つの引数 (ファイルまたはバッファー、書式設定文字列)|
|`_snprintf_s`|最初の 3 つの引数 (ファイルまたはバッファー、カウント、書式設定文字列)|
|`_open`|最初の 2 つの引数 (パス、`_open` フラグ)|
|`_sopen_s`|最初の 3 つの引数 (パス、`_open` フラグ、共有モード)|
|`_execl`, `_execle`, `_execlp`, `_execlpe`|最初の 2 つの引数 (パス、最初の引数のポインター)|
|`_spawnl`, `_spawnle`, `_spawnlp`, `_spawnlpe`|最初の 3 つの引数 (モード フラグ、パス、最初の引数のポインター)|

コンパイラでは、ワイド文字版のこれらの関数についても同じ制限付きの型チェックを行います。

## <a name="see-also"></a>こちらもご覧ください

[C ランタイム (CRT) と C++ 標準ライブラリ (STL) `.lib` ファイル](../c-runtime-library/crt-library-features.md)
