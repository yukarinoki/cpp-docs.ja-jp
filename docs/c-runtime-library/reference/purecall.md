---
description: '詳細については、次を参照してください: _purecall'
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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: df52d7383685f3ce183562d8789b710fd7587acd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97209452"
---
# <a name="_purecall"></a>_purecall

純粋仮想関数が呼び出された場合の、既定のエラー ハンドラーです。 純粋仮想メンバー関数が呼び出されると、コンパイラによってこの関数を呼び出すコードが生成されます。

## <a name="syntax"></a>構文

```C
extern "C" int __cdecl _purecall();
```

## <a name="remarks"></a>解説

**_Purecall** 関数は、microsoft C++ コンパイラの microsoft 固有の実装の詳細です。 この関数はコードで直接呼び出されるものではなく、パブリック ヘッダー宣言がありません。 C ランタイム ライブラリのパブリック エクスポートであるため、ここで説明しています。

純粋仮想関数には実装がないため、この関数への呼び出しはエラーになります。 コンパイラは、純粋仮想関数が呼び出されたときに **_purecall** エラーハンドラー関数を呼び出すコードを生成します。 既定では、 **_purecall** はプログラムを終了します。 プロセスに対して設定されている場合、 **_purecall** 関数は、終了する前に **_purecall_handler** 関数を呼び出します。 純粋仮想関数の呼び出し用に独自のエラー ハンドラーの関数をインストールして呼び出しをキャッチし、デバッグまたはレポート作成に使用することができます。 独自のエラーハンドラーを使用するには、 **_purecall_handler** シグネチャを持つ関数を作成し、 [_set_purecall_handler](get-purecall-handler-set-purecall-handler.md) を使用してそれを現在のハンドラーにします。

既定では、この関数のグローバル状態はアプリケーションにスコープが設定されています。 これを変更するには、「 [CRT でのグローバル状態](../global-state.md)」を参照してください。

## <a name="requirements"></a>要件

**_Purecall** 関数には、ヘッダー宣言がありません。 **_Purecall_handler** typedef はで定義されて \<stdlib.h> います。

## <a name="see-also"></a>関連項目

[アルファベット順の関数リファレンス](crt-alphabetical-function-reference.md)<br/>
[_get_purecall_handler、_set_purecall_handler](get-purecall-handler-set-purecall-handler.md)<br/>
