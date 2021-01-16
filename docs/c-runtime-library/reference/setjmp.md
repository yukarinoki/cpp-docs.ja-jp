---
title: setjmp
description: Setjmp の API リファレンス;これにより、プログラムの現在の状態が保存されます。
ms.date: 1/14/2021
api_name:
- setjmp
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
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- setjmp
helpviewer_keywords:
- programs [C++], saving states
- current state
- setjmp function
ms.assetid: 684a8b27-e8eb-455b-b4a8-733ca1cbd7d2
ms.openlocfilehash: 0830cf253553523747a815efc950d4cf75b36647
ms.sourcegitcommit: 1cd8f8a75fd036ffa57bc70f3ca869042d8019d4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/15/2021
ms.locfileid: "98242645"
---
# `setjmp`

プログラムの現在の状態を保存します。

## <a name="syntax"></a>構文

```C
int setjmp(
   jmp_buf env
);
```

### <a name="parameters"></a>パラメーター

*`env`*\
環境が格納されている変数。

## <a name="return-value"></a>戻り値

スタックの環境を保存した後に 0 を返します。 **`setjmp`** 呼び出しのためにがを返す場合 `longjmp` は、の *値* 引数を返し `longjmp` ます。または、の *値* 引数が0の場合は `longjmp` **`setjmp`** 1 を返します。 エラーの戻り値はありません。

## <a name="remarks"></a>注釈

関数は、 **`setjmp`** を使用して、後で復元できるスタック環境を保存し `longjmp` ます。 とを一緒に使用する **`setjmp`** と、 `longjmp` ローカルではないを実行する方法を提供し **`goto`** ます。 通常は、通常の呼び出し規約または戻り値の規則を使用せずに、以前に呼び出されたルーチンのエラー処理または復旧コードに実行制御を渡すために使用されます。

の呼び出しは、 **`setjmp`** 現在のスタック環境をに保存 *`env`* します。 の後続の呼び出しは、 `longjmp` 保存された環境を復元し、対応する呼び出しの直後のポイントに制御を戻し **`setjmp`** ます。 コントロールを受け取るルーチンにアクセスできるすべての変数 (レジスタ変数を除く) には、`longjmp` が呼び出されたときに保持していた値が含まれます。

を使用して、 **`setjmp`** ネイティブコードからマネージコードに移動することはできません。

**Microsoft 固有の仕様**

Windows 上の Microsoft C++ コードでは、は、 **`longjmp`** 例外処理コードと同じスタックアンワインドセマンティクスを使用します。 C++ 例外を発生させるのと同じ場所で、を安全に使用できます。 ただし、この使用はポータブルではなく、いくつかの重要な注意事項があります。 詳細については、[`longjmp`](longjmp.md) を参照してください。

**Microsoft 固有の仕様はここまで**

> [!NOTE]
> 移植可能な C++ コードでは、 `setjmp` c++ オブジェクトのセマンティクスを想定してサポートすることはできません `longjmp` 。 具体的には、 `setjmp` / `longjmp` とを置き換える場合、呼び出しペアの動作が未定義である `setjmp` ため、 `longjmp` **`catch`** **`throw`** 任意の自動オブジェクトに対して自明ではないデストラクターが呼び出されます。 C++ プログラムでは、C++ 例外処理機構を使用することをお勧めします。

詳細については、「」 [ `setjmp` および `longjmp` ](../../cpp/using-setjmp-longjmp.md)「」を参照してください。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**`setjmp`**|\<setjmp.h>|

互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="example"></a>例

の例を参照してください [`_fpreset`](fpreset.md) 。

## <a name="see-also"></a>参照

[プロセスと環境の制御](../../c-runtime-library/process-and-environment-control.md)\
[`longjmp`](longjmp.md)
