---
description: 遅延読み込みヘルパー関数の詳細情報
title: 遅延読み込みヘルパー関数について
ms.date: 01/19/2021
helpviewer_keywords:
- delayed loading of DLLs, helper function
- __delayLoadHelper2 function
- delayimp.lib
- __delayLoadHelper function
- delayhlp.cpp
- delayimp.h
- helper functions
ms.openlocfilehash: 6108e896b6d7a370f2b4d6ab8f5baa880112a21e
ms.sourcegitcommit: c20734f18d3d49bb38b1628c68b53b54b3eeeb03
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2021
ms.locfileid: "99522743"
---
# <a name="understand-the-delay-load-helper-function"></a>遅延読み込みヘルパー関数について

リンカーでサポートされる遅延読み込みのヘルパー関数は、実行時に実際に DLL を読み込むものです。 ヘルパー関数を変更して、その動作をカスタマイズできます。 で指定されたヘルパー関数を使用する代わりに *`delayimp.lib`* 、独自の関数を記述し、プログラムにリンクします。 1つのヘルパー関数は、遅延読み込みされたすべての Dll に対して機能します。

DLL またはインポートの名前に基づいて特定の処理を実行する場合は、独自のバージョンのヘルパー関数を指定できます。

ヘルパー関数は、次のアクションを実行します。

- 既に読み込まれているかどうかを確認するために、格納されているハンドルをライブラリに対してチェックします。

- `LoadLibrary`DLL の読み込みを試行するための呼び出し

- `GetProcAddress`を呼び出して、プロシージャのアドレスを取得します。

- 現在読み込まれているエントリポイントを呼び出すために、遅延インポート読み込みサンクに戻ります。

ヘルパー関数は、次の各アクションの後で、プログラム内の通知フックにコールバックできます。

- ヘルパー関数の開始時

- `LoadLibrary`ヘルパー関数でが呼び出される直前

- `GetProcAddress`ヘルパー関数でが呼び出される直前

- `LoadLibrary`ヘルパー関数でのの呼び出しが失敗した場合

- `GetProcAddress`ヘルパー関数でのの呼び出しが失敗した場合

- ヘルパー関数の処理が完了した後

これらのフックポイントは、遅延インポート読み込みサンクに戻る以外は、何らかの方法でヘルパールーチンの通常の処理を変更する値を返すことができます。

既定のヘルパーコードは、 *`delayhlp.cpp`* MSVC ディレクトリ内のとにあり *`delayimp.h`* *`include`* ます。 *`delayimp.lib`* *`lib`* ターゲットアーキテクチャの MSVC ディレクトリにコンパイルされます。 独自のヘルパー関数を記述しない限り、このライブラリをコンパイルに含める必要があります。

## <a name="delay-load-helper-calling-conventions-parameters-and-return-type"></a><a name="calling-conventions-parameters-and-return-type"></a> 遅延読み込みヘルパー呼び出し規約、パラメーター、および戻り値の型

遅延読み込みヘルパールーチンのプロトタイプは次のとおりです。

```C
FARPROC WINAPI __delayLoadHelper2(
    PCImgDelayDescr pidd,
    FARPROC * ppfnIATEntry
);
```

### <a name="parameters"></a>パラメーター

*`pidd`*\
**`const`** `ImgDelayDescr` さまざまなインポート関連データのオフセット、バインディング情報のタイムスタンプ、記述子コンテンツに関する詳細情報を提供する一連の属性を格納するへのポインター。 現在、属性は1つだけです `dlattrRva` 。これは、記述子のアドレスが相対仮想アドレスであることを示します。 詳細については、「」の宣言を参照してください *`delayimp.h`* 。

遅延記述子 () 内のポインターは、 `ImgDelayDescr` *`delayimp.h`* 相対仮想アドレス (RVAs) を使用して、32ビットプログラムと64ビットプログラムの両方で期待どおりに動作します。 これらを使用するには、「」にある関数を使用して、これらの RVAs をポインターに戻し `PFromRva` *`delayhlp.cpp`* ます。 この関数は、記述子の各フィールドに対して使用して、32ビットまたは64ビットのポインターに変換することができます。 既定の遅延読み込みヘルパー関数は、例として使用するのに適したテンプレートです。

構造体の定義につい `PCImgDelayDescr` ては、「 [構造体と定数の定義](#structure-and-constant-definitions)」を参照してください。

*`ppfnIATEntry`*\
遅延読み込みインポートアドレステーブル (IAT) 内のスロットへのポインター。 これは、インポートされた関数のアドレスで更新されるスロットです。 ヘルパールーチンは、この場所に返されるのと同じ値を格納する必要があります。

### <a name="expected-return-values"></a>予期される戻り値

ヘルパー関数が成功した場合は、インポートされた関数のアドレスが返されます。

関数が失敗した場合は、構造化例外が発生し、0が返されます。 発生される例外には 3 種類あります。

- パラメーターが無効です。の属性が正しく指定されていない場合に発生し *`pidd`* ます。 これを回復不能なエラーとして扱います。

- 指定された DLL で `LoadLibrary` が失敗しました。

- `GetProcAddress` の失敗。

これらの例外を処理するのはお客様の責任です。 詳細については、「 [エラー処理と通知](error-handling-and-notification.md)」を参照してください。

### <a name="remarks"></a>解説

ヘルパー関数の呼び出し規約はです **`__stdcall`** 。 戻り値の型は関係ありません。したがって、 `FARPROC` が使用されます。 この関数には C リンケージがあります。これは、C++ コードで宣言されている場合に、によってラップされる必要があることを意味し `extern "C"` ます。 このラッパーはマクロによって自動的に処理さ `ExternC` れます。

ヘルパールーチンを通知フックとして使用するには、コードで返される適切な関数ポインターを指定する必要があります。 リンカーが生成するサンク コードは、その戻り値をインポートの実際のターゲットとして扱い、そこに直接ジャンプします。 ヘルパールーチンを通知フックとして使用しない場合は、渡された関数ポインターの位置であるヘルパー関数の戻り値をに格納し `ppfnIATEntry` ます。

## <a name="sample-hook-function"></a>サンプルのフック関数

次のコードは、基本的なフック関数を実装する方法を示しています。

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
            // If you choose, you may handle the failure by returning
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
and then at global scope somewhere:

ExternC const PfnDliHook __pfnDliNotifyHook2 = delayHook;
ExternC const PfnDliHook __pfnDliFailureHook2 = delayHook;
*/
```

## <a name="delay-load-structure-and-constant-definitions"></a><a name="structure-and-constant-definitions"></a> 遅延読み込みの構造体と定数の定義

既定の遅延読み込みヘルパールーチンは、いくつかの構造体を使用してフック関数との通信を行い、例外が発生したときに使用します。 これらの構造体は、で定義されて *`delayimp.h`* います。 次に示すのは、マクロ、typedef、通知とエラーの値、情報の構造、およびフックに渡されるポインターからフックへの関数の型です。

```C
#define _DELAY_IMP_VER  2

#if defined(__cplusplus)
#define ExternC extern "C"
#else
#define ExternC extern
#endif

typedef IMAGE_THUNK_DATA *          PImgThunkData;
typedef const IMAGE_THUNK_DATA *    PCImgThunkData;
typedef DWORD                       RVA;

typedef struct ImgDelayDescr {
    DWORD           grAttrs;        // attributes
    RVA             rvaDLLName;     // RVA to dll name
    RVA             rvaHmod;        // RVA of module handle
    RVA             rvaIAT;         // RVA of the IAT
    RVA             rvaINT;         // RVA of the INT
    RVA             rvaBoundIAT;    // RVA of the optional bound IAT
    RVA             rvaUnloadIAT;   // RVA of optional copy of original IAT
    DWORD           dwTimeStamp;    // 0 if not bound,
                                    // O.W. date/time stamp of DLL bound to (Old BIND)
    } ImgDelayDescr, * PImgDelayDescr;

typedef const ImgDelayDescr *   PCImgDelayDescr;

enum DLAttr {                   // Delay Load Attributes
    dlattrRva = 0x1,                // RVAs are used instead of pointers
                                    // Having this set indicates a VC7.0
                                    // and above delay load descriptor.
    };

//
// Delay load import hook notifications
//
enum {
    dliStartProcessing,             // used to bypass or note helper only
    dliNoteStartProcessing = dliStartProcessing,

    dliNotePreLoadLibrary,          // called just before LoadLibrary, can
                                    //  override w/ new HMODULE return val
    dliNotePreGetProcAddress,       // called just before GetProcAddress, can
                                    //  override w/ new FARPROC return value
    dliFailLoadLib,                 // failed to load library, fix it by
                                    //  returning a valid HMODULE
    dliFailGetProc,                 // failed to get proc address, fix it by
                                    //  returning a valid FARPROC
    dliNoteEndProcessing,           // called after all processing is done, no
                                    //  bypass possible at this point except
                                    //  by longjmp()/throw()/RaiseException.
    };

typedef struct DelayLoadProc {
    BOOL                fImportByName;
    union {
        LPCSTR          szProcName;
        DWORD           dwOrdinal;
        };
    } DelayLoadProc;

typedef struct DelayLoadInfo {
    DWORD               cb;         // size of structure
    PCImgDelayDescr     pidd;       // raw form of data (everything is there)
    FARPROC *           ppfn;       // points to address of function to load
    LPCSTR              szDll;      // name of dll
    DelayLoadProc       dlp;        // name or ordinal of procedure
    HMODULE             hmodCur;    // the hInstance of the library we have loaded
    FARPROC             pfnCur;     // the actual function that will be called
    DWORD               dwLastError;// error received (if an error notification)
    } DelayLoadInfo, * PDelayLoadInfo;

typedef FARPROC (WINAPI *PfnDliHook)(
    unsigned        dliNotify,
    PDelayLoadInfo  pdli
    );
```

## <a name="calculate-necessary-values-for-delay-loading"></a><a name="calculate-necessary-values"></a> 遅延読み込みに必要な値を計算します

遅延読み込みヘルパールーチンでは、2つの重要な情報を計算する必要があります。 では、 *`delayhlp.cpp`* この情報を計算するためにのインライン関数が2つあります。

- 1つ目のは、 `IndexFromPImgThunkData` 現在のインポートのインデックスを3つの異なるテーブル (インポートアドレステーブル (IAT)、バインドされたインポートアドレステーブル (BIAT)、およびバインドされていないインポートアドレステーブル (UIAT)) に計算します。

- 2番目のは、 `CountOfImports` 有効な IAT 内のインポートの数をカウントします。

```C
// utility function for calculating the index of the current import
// for all the tables (INT, BIAT, UIAT, and IAT).
__inline unsigned
IndexFromPImgThunkData(PCImgThunkData pitdCur, PCImgThunkData pitdBase) {
    return pitdCur - pitdBase;
    }

// utility function for calculating the count of imports given the base
// of the IAT. NB: this only works on a valid IAT!
__inline unsigned
CountOfImports(PCImgThunkData pitdBase) {
    unsigned        cRet = 0;
    PCImgThunkData  pitd = pitdBase;
    while (pitd->u1.Function) {
        pitd++;
        cRet++;
        }
    return cRet;
    }
```

## <a name="support-unload-of-a-delay-loaded-dll"></a><a name="unload-a-delay-loaded-dll"></a> 遅延読み込みされた DLL のアンロードをサポートする

遅延読み込みされた DLL が読み込まれると、既定の遅延読み込みヘルパーは、遅延読み込み記述子に、そのフィールドに元のインポートアドレステーブル (IAT) のポインターとコピーが含まれているかどうかを確認し `pUnloadIAT` ます。 その場合、ヘルパーは、リスト内のポインターをインポート遅延記述子に保存します。 このエントリにより、ヘルパー関数は dll を名前で検索できるようになり、DLL の明示的なアンロードがサポートされます。

遅延読み込みされた DLL を明示的にアンロードするための、関連する構造体と関数を次に示します。

```cpp
//
// Unload support from delayimp.h
//

// routine definition; takes a pointer to a name to unload

ExternC
BOOL WINAPI
__FUnloadDelayLoadedDLL2(LPCSTR szDll);

// structure definitions for the list of unload records
typedef struct UnloadInfo * PUnloadInfo;
typedef struct UnloadInfo {
    PUnloadInfo     puiNext;
    PCImgDelayDescr pidd;
    } UnloadInfo;

// from delayhlp.cpp
// the default delay load helper places the unloadinfo records in the
// list headed by the following pointer.
ExternC
PUnloadInfo __puiHead;
```

`UnloadInfo`構造体は、およびの実装をおよびとして使用する C++ クラスを使用して実装され `LocalAlloc` `LocalFree` `operator new` `operator delete` ます。 これらのオプションは、 `__puiHead` リストの先頭としてを使用する標準のリンクリストに保持されます。

を呼び出すと `__FUnloadDelayLoadedDLL` 、読み込まれた dll の一覧で指定した名前の検索が試行されます。 (完全一致が必要です)。見つかった場合は、の IAT のコピー `pUnloadIAT` が、実行されている iat の先頭にコピーされ、サンクポインターが復元されます。 次に、を使用してライブラリが解放され、 `FreeLibrary` 一致するレコードがリストからリンク解除されて削除され、 `UnloadInfo` `TRUE` が返されます。

関数の引数で `__FUnloadDelayLoadedDLL2` は、大文字と小文字が区別されます。 たとえば、次のように指定します。

```cpp
__FUnloadDelayLoadedDLL2("user32.dll");
```

ではありません。

```cpp
__FUnloadDelayLoadedDLL2("User32.DLL");
```

遅延読み込みされた DLL のアンロードの例については、「 [遅延読み込みされた dll の明示的なアンロード](linker-support-for-delay-loaded-dlls.md)」を参照してください。

## <a name="develop-your-own-delay-load-helper-function"></a><a name="develop-your-own-helper-function"></a> 独自の遅延読み込みヘルパー関数を開発する

独自のバージョンの遅延読み込みヘルパールーチンを用意することもできます。 独自のルーチンでは、DLL またはインポートの名前に基づいて特定の処理を行うことができます。 独自のコードを挿入するには、次の2つの方法があります。指定されたコードに基づいて独自のヘルパー関数をコーディングすることができます。 または、指定されたヘルパーをフックして、 [通知フック](error-handling-and-notification.md#notification-hooks)を使用して独自の関数を呼び出します。

### <a name="code-your-own-helper"></a>独自のヘルパーをコーディングする

独自のヘルパールーチンを作成するのは簡単です。 既存のコードを新しい関数のガイドとして使用することができます。 関数では、既存のヘルパーと同じ呼び出し規約を使用する必要があります。 また、リンカーによって生成されたサンクに戻る場合は、適切な関数ポインターを返す必要があります。 コードを作成したら、呼び出しを満たすか、呼び出しを取得することができます。

### <a name="use-the-start-processing-notification-hook"></a>処理開始通知フックを使用する

通知の既定のヘルパーと同じ値を受け取るユーザー指定の通知フック関数への新しいポインターを提供するのが最も簡単な方法です `dliStartProcessing` 。 その時点で、フック関数は実質的に新しいヘルパー関数になります。既定のヘルパーに正常に戻ると、既定のヘルパーでの後続の処理がすべてバイパスされるためです。

## <a name="see-also"></a>関連項目

[リンカーによる DLL の遅延読み込み](linker-support-for-delay-loaded-dlls.md#explicitly-unload-a-delay-loaded-dll)
