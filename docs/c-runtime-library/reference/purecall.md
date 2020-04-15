---
title: _purecall
ms.date: 4/2/2020
api_name:
- _purecall
- _o__purecall
api_location:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ntoskrnl.exe
- ucrtbase.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- purecall
- _purecall
helpviewer_keywords:
- _purecall function
- purecall function
ms.assetid: 56135d9b-3403-4e22-822d-e714523801cc
ms.openlocfilehash: f841bc70a4a5365bb9cc6086dd752bd2a1b583ed
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81338483"
---
# <a name="_purecall"></a>_purecall

純粋仮想関数が呼び出された場合の、既定のエラー ハンドラーです。 純粋仮想メンバー関数が呼び出されると、コンパイラによってこの関数を呼び出すコードが生成されます。

## <a name="syntax"></a>構文

```C
extern "C" int __cdecl _purecall();
```

## <a name="remarks"></a>解説

**_purecall**関数は、マイクロソフト固有の実装の詳細です。 この関数はコードで直接呼び出されるものではなく、パブリック ヘッダー宣言がありません。 C ランタイム ライブラリのパブリック エクスポートであるため、ここで説明しています。

純粋仮想関数には実装がないため、この関数への呼び出しはエラーになります。 コンパイラは、純粋仮想関数が呼び出されたときに **_purecall**エラー ハンドラ関数を呼び出すコードを生成します。 既定では **、_purecall**プログラムを終了します。 終了する前に **、_purecall**関数は、プロセスに対して設定されている場合 **、_purecall_handler**関数を呼び出します。 純粋仮想関数の呼び出し用に独自のエラー ハンドラーの関数をインストールして呼び出しをキャッチし、デバッグまたはレポート作成に使用することができます。 独自のエラー ハンドラを使用するには **、_purecall_handler**シグネチャを持つ関数を作成し[、_set_purecall_handler](get-purecall-handler-set-purecall-handler.md)を使用して現在のハンドラにします。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

## <a name="requirements"></a>必要条件

**_purecall**関数にヘッダー宣言がありません。 **_purecall_handler**の型定義は stdlib.h>で\<定義されます。

## <a name="see-also"></a>関連項目

[関数リファレンス (アルファベット順)](crt-alphabetical-function-reference.md)<br/>
[_get_purecall_handler、_set_purecall_handler](get-purecall-handler-set-purecall-handler.md)<br/>
