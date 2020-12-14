---
description: 詳細については、「呼び出し規約、パラメーター、および戻り値の型」を参照してください。
title: 呼び出し規則、パラメーター、および戻り値の型
ms.date: 02/13/2019
helpviewer_keywords:
- calling conventions, helper functions
- helper functions, calling conventions
- helper functions, return types
ms.assetid: 0ffa4558-6005-4803-be95-7a8ec8837660
ms.openlocfilehash: f840ecbe3364f293e9445239984ad375eed48aac
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97182529"
---
# <a name="calling-conventions-parameters-and-return-type"></a>呼び出し規則、パラメーター、および戻り値の型

ヘルパー ルーチンのプロトタイプ: 

```
FARPROC WINAPI __delayLoadHelper2(
    PCImgDelayDescr pidd,
    FARPROC * ppfnIATEntry
);
```

### <a name="parameters"></a>パラメーター

*pidd*<br/>
**`const`** `ImgDelayDescr` さまざまなインポート関連データのオフセット、バインディング情報のタイムスタンプ、記述子コンテンツに関する詳細情報を提供する一連の属性を格納するへのポインター。 現在、属性は1つだけです `dlattrRva` 。これは、記述子のアドレスが相対仮想アドレスであることを示します。 詳細については、「 *delayimp. h*」の宣言を参照してください。

構造体の定義につい `PCImgDelayDescr` ては、「 [構造体と定数の定義](structure-and-constant-definitions.md)」を参照してください。

*ppfnIATEntry*<br/>
遅延読み込みインポートアドレステーブル (IAT) のスロットへのポインター。インポートされた関数のアドレスで更新されます。 ヘルパールーチンは、この場所に返されるのと同じ値を格納する必要があります。

## <a name="expected-return-values"></a>予想戻り値

関数が成功した場合、インポートされた関数のアドレスを返します。

関数が失敗した場合、例外を発生させて 0 を返します。 発生される例外には 3 種類あります。

- 無効なパラメーター。`pidd` の属性が正しく指定されない場合に生じます。

- 指定された DLL で `LoadLibrary` が失敗しました。

- `GetProcAddress` の失敗。

これらの例外を処理するのはお客様の責任です。

## <a name="remarks"></a>解説

ヘルパー関数の呼び出し規約はです **`__stdcall`** 。 戻り値の型は関係ありません。したがって、FARPROC が使用されます。 この機能には C リンケージがあります。

遅延読み込みヘルパーの戻り値は、ヘルパー ルーチンを通知フックとして使用するつもりでない限り、渡された関数ポインターの場所に保存する必要があります。 その場合、戻すべき適切な関数ポインターを探すコードが必要です。 リンカーが生成するサンク コードは、その戻り値をインポートの実際のターゲットとして扱い、そこに直接ジャンプします。

## <a name="sample"></a>サンプル

次のコードは、簡単なフック関数を実装する方法を示しています。

```C
FARPROC WINAPI delayHook(unsigned dliNotify, PDelayLoadInfo pdli)
{
    switch (dliNotify) {
        case dliStartProcessing :

            // If you want to return control to the helper, return 0.
            // Otherwise, return a pointer to a FARPROC helper function
            // that will be used instead, thereby bypassing the rest
            // of the helper.

            break;

        case dliNotePreLoadLibrary :

            // If you want to return control to the helper, return 0.
            // Otherwise, return your own HMODULE to be used by the
            // helper instead of having it call LoadLibrary itself.

            break;

        case dliNotePreGetProcAddress :

            // If you want to return control to the helper, return 0.
            // If you choose you may supply your own FARPROC function
            // address and bypass the helper's call to GetProcAddress.

            break;

        case dliFailLoadLib :

            // LoadLibrary failed.
            // If you don't want to handle this failure yourself, return 0.
            // In this case the helper will raise an exception
            // (ERROR_MOD_NOT_FOUND) and exit.
            // If you want to handle the failure by loading an alternate
            // DLL (for example), then return the HMODULE for
            // the alternate DLL. The helper will continue execution with
            // this alternate DLL and attempt to find the
            // requested entrypoint via GetProcAddress.

            break;

        case dliFailGetProc :

            // GetProcAddress failed.
            // If you don't want to handle this failure yourself, return 0.
            // In this case the helper will raise an exception
            // (ERROR_PROC_NOT_FOUND) and exit.
            // If you choose you may handle the failure by returning
            // an alternate FARPROC function address.

            break;

        case dliNoteEndProcessing :

            // This notification is called after all processing is done.
            // There is no opportunity for modifying the helper's behavior
            // at this point except by longjmp()/throw()/RaiseException.
            // No return value is processed.

            break;

        default :

            return NULL;
    }

    return NULL;
}

/*
and then at global scope somewhere
const PfnDliHook __pfnDliNotifyHook2 = delayHook;
*/
```

## <a name="see-also"></a>関連項目

[ヘルパー関数について](understanding-the-helper-function.md)
