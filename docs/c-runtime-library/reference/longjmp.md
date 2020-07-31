---
title: longjmp
ms.date: 08/14/2018
api_name:
- longjmp
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
- ucrtbase.dll
- ntoskrnl.exe
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- longjmp
helpviewer_keywords:
- restoring stack environment and execution locale
- longjmp function
ms.assetid: 0e13670a-5130-45c1-ad69-6862505b7a2f
ms.openlocfilehash: 4f737818afe7136262362e4fe996745064568758
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87218560"
---
# <a name="longjmp"></a>longjmp

呼び出しによって設定されたスタック環境と実行ロケールを復元し `setjmp` ます。

## <a name="syntax"></a>構文

```C
void longjmp(
   jmp_buf env,
   int value
);
```

### <a name="parameters"></a>パラメーター

*エンベロープ*<br/>
環境が格納されている変数。

*value*<br/>
`setjmp` 呼び出しに返される値。

## <a name="remarks"></a>解説

**Longjmp**関数は、前にで*env*に保存したスタック環境と実行ロケールを復元し `setjmp` ます。 `setjmp`と**longjmp**は、非ローカルのを実行する方法を提供します **`goto`** 。通常は、通常の呼び出し規約と戻り値の規則を使用せずに、以前に呼び出されたルーチンのエラー処理または復旧コードに実行制御を渡すために使用されます。

を呼び出すと、 `setjmp` 現在のスタック環境が*env*に保存されます。 次に**longjmp**を呼び出すと、保存した環境が復元され、対応する呼び出しの直後のポイントに制御が戻り `setjmp` ます。 実行は、*value* が `setjmp` 呼び出しによって返されたかのように再開されます。 コントロールを受け取るルーチンからアクセスできるすべての変数 (レジスタ変数を除く) の値には、 **longjmp**が呼び出されたときに取得した値が含まれます。 レジスタ変数の値は予測できません。 `setjmp` によって返される値は、0 以外である必要があります。 *value* が 0 として渡される場合、実際の戻り値では 1 が代入されます。

**Microsoft 固有の仕様**

Windows 上の Microsoft C++ コードでは、 **longjmp**は例外処理コードと同じスタックアンワインドセマンティクスを使用します。 C++ 例外を発生させるのと同じ場所で、を安全に使用できます。 ただし、この使用方法はポータブルではなく、いくつかの重要な注意事項が付属しています。

を呼び出した関数の前に**longjmp**を呼び出すだけです。 `setjmp` それ以外の場合、結果は予測できません。

**Longjmp**を使用する場合は、次の制限事項に注意してください。

- レジスタ変数の値は変わらないと見なさないでください。 を呼び出す場合のレジスタ変数の値は、 `setjmp` **longjmp**の実行後に適切な値に復元されない可能性があります。

- 割り込みが浮動小数点例外によって引き起こされる場合を除き、割り込み処理ルーチンから制御を移すために**longjmp**を使用しないでください。 この場合、プログラムは、 [_fpreset](fpreset.md)を呼び出すことによって浮動小数点数値演算パッケージを最初に再初期化すると、 **longjmp**を使用して割り込みハンドラーから戻る可能性があります。

- Windows コードによって直接または間接的に呼び出されたコールバックルーチンからコントロールを転送する場合は、 **longjmp**を使用しないでください。

- コードが **/ehs**または **/ehsc**を使用してコンパイルされ、 **longjmp**呼び出しを含む関数がの場合、 **`noexcept`** その関数のローカルオブジェクトはスタックアンワインド中に破棄されされない可能性があります。

**Microsoft 固有の仕様はここまで**

> [!NOTE]
> 移植可能な C++ コードでは、 `setjmp` c++ オブジェクトのセマンティクスを想定してサポートすることはできません `longjmp` 。 具体的には、 `setjmp` / `longjmp` とを置き換える場合、呼び出しペアの動作が未定義である `setjmp` ため、 `longjmp` **`catch`** **`throw`** 任意の自動オブジェクトに対して自明ではないデストラクターが呼び出されます。 C++ プログラムでは、C++ 例外処理機構を使用することをお勧めします。

詳細については、「[setjmp/longjmp の使用](../../cpp/using-setjmp-longjmp.md)」を参照してください。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**longjmp**|\<setjmp.h>|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

「[_fpreset](fpreset.md)」の例を参照してください。

## <a name="see-also"></a>関連項目

[プロセスと環境の制御](../../c-runtime-library/process-and-environment-control.md)<br/>
[setjmp](setjmp.md)
