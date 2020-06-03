---
title: 呼び出し規則、パラメーター、および戻り値の型
ms.date: 02/13/2019
helpviewer_keywords:
- calling conventions, helper functions
- helper functions, calling conventions
- helper functions, return types
ms.assetid: 0ffa4558-6005-4803-be95-7a8ec8837660
ms.openlocfilehash: 90767141337512b053bb06a40823c4a22a8a4823
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80169748"
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
さまざまなインポート関連データのオフセット、バインディング情報のタイムスタンプ、記述子コンテンツに関する詳細情報を提供する一連の属性を格納している `ImgDelayDescr` への `const` ポインター。 現時点では、属性が1つだけ存在します。 `dlattrRva`は、記述子内のアドレスが相対仮想アドレスであることを示します。 詳細については、「 *delayimp. h*」の宣言を参照してください。

`PCImgDelayDescr` 構造体の定義については、「[構造体と定数の定義](structure-and-constant-definitions.md)」を参照してください。

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

ヘルパー関数の呼び出し規則は `__stdcall` です。 戻り値の型は関係ありません。したがって、FARPROC が使用されます。 この機能には C リンケージがあります。

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

## <a name="see-also"></a>参照

[ヘルパー関数について](understanding-the-helper-function.md)
