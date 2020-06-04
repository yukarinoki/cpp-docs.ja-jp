---
title: EXPORTS
ms.date: 09/07/2018
f1_keywords:
- EXPORTS
helpviewer_keywords:
- EXPORTS .def file statement
ms.assetid: dbcd7579-b855-44c4-bd27-931e157657f7
ms.openlocfilehash: 9ede0d3b53c975298dea3d1331bc0fb00ac246b2
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81328259"
---
# <a name="exports"></a>EXPORTS

関数またはデータのエクスポート名または序数を指定する 1 つ以上のエクスポート定義のセクションを導入します。 各定義は個別の行に指定する必要があります。

```DEF
EXPORTS
   definition
```

## <a name="remarks"></a>解説

最初の*定義*は、キーワードと同じ行に`EXPORTS`することも、後続の行に置く場合があります。 .DEF ファイルには、1 つ以上の `EXPORTS` ステートメントを含めることができます。

エクスポート*定義*の構文は次のとおりです。

> *エントリ名*\[__=__*internal_name*|*other_module.exported_name*[ \[ **\@**_序数_\[ **NONAME**] ] [ \[ \[**プライベート**] |\[ **[ ]**

*エントリ名*は、エクスポートする関数または変数名です。 これは必須です。 エクスポートする名前が DLL の名前と異なる場合は *、internal_name*を使用して DLL にエクスポートの名前を指定します。 たとえば、DLL で関数 `func1` をエクスポートし、呼び出し元がそれを `func2` として使用する場合は、次のように指定します。

```DEF
EXPORTS
   func2=func1
```

エクスポートする名前が他のモジュールの名前である場合は、dll で*other_module.exported_name*を使用してエクスポートの名前を指定します。 たとえば、DLL で関数 `other_module.func1` をエクスポートし、呼び出し元がそれを `func2` として使用する場合は、次のように指定します。

```DEF
EXPORTS
   func2=other_module.func1
```

エクスポートする名前が序数でエクスポートされる別のモジュールの名前である場合は、 *other_module*を使用して DLL でエクスポートの序数を指定します。__#__*序数*. たとえば、DLL が関数を序数 42 の他のモジュールからエクスポートし、呼び出し元に関数を として`func2`使用する場合は、次のように指定します。

```DEF
EXPORTS
   func2=other_module.#42
```

MSVC コンパイラは C++ 関数の名前装飾を使用するため、装飾名*を使用internal_name*か、ソース コードで使用`extern "C"`してエクスポートされた関数を定義する必要があります。 コンパイラは、[アンダー](../../cpp/stdcall.md)スコア ( ) プレフィックスと、引数リストのバイト\_数 (10 進数)\@で構成される接尾辞を持つ __stdcall 呼び出し規約を使用する C 関数も修飾します。

コンパイラによって生成された装飾名を検索するには[、DUMPBIN](dumpbin-reference.md)ツールまたはリンカー [/MAP](map-generate-mapfile.md)オプションを使用します。 装飾名はコンパイラ固有です。 装飾名を .DEF ファイルにエクスポートする場合、DLL にリンクする実行可能ファイルも同じバージョンのコンパイラを使用してビルドする必要があります。 これにより、呼び出し元の装飾名は .DEF ファイルのエクスポート名と一致します。

\@*序数*を使用して、関数名ではなく数値を DLL のエクスポート テーブルに入るように指定できます。 多くの Windows DLL で、レガシ コードをサポートするために序数がエクスポートされます。 DLL のサイズを最小限に抑えるのに役立つため、16 ビットの Windows コードでは序数を使用することが一般的でした。 DLL のクライアントが従来のサポートに必要な場合を除き、関数を序数でエクスポートすることはお勧めしません。 .LIB ファイルには序数と関数のマッピングが含まれているため、DLL を使用するプロジェクトでは通常と同様に関数名を使用できます。

オプションの**NONAME**キーワードを使用すると、序数のみでエクスポートし、結果の DLL 内のエクスポート テーブルのサイズを小さくすることができます。 ただし、DLL で[GetProcAddress](/windows/win32/api/libloaderapi/nf-libloaderapi-getprocaddress)を使用する場合は、名前が有効でないため序数を知っている必要があります。

オプションのキーワード**PRIVATE**を指定すると、LINK によって生成されたインポート・ライブラリーに*エントリー名*が組み込まれないようにします。 同じく LINK によって生成されるイメージ内のエクスポートには影響しません。

オプションのキーワード**DATA は**、エクスポートがコードではなくデータであることを指定します。 次の例では、`exported_global` という名前のデータ変数をエクスポートする方法を示します。

```DEF
EXPORTS
   exported_global DATA
```

定義をエクスポートするには 4 つの方法があり、それらを推奨される順序で示します。

1. ソース コードの[__declspec(dllexport)](../../cpp/dllexport-dllimport.md)キーワード

1. .DEF ファイルでの `EXPORTS` ステートメント

1. LINK コマンドで[の /EXPORT](export-exports-a-function.md)指定

1. ソース コード内の[、](../../preprocessor/comment-c-cpp.md)フォーム`#pragma comment(linker, "/export: definition ")`のコメント ディレクティブ。 次の例は、`PlainFuncName``_PlainFuncName@4`関数宣言の前に#pragmaコメント ディレクティブを示しています。

    ```cpp
    #pragma comment(linker, "/export:PlainFuncName=_PlainFuncName@4")
    BOOL CALLBACK PlainFuncName( Things * lpParams)
    ```

#pragma ディレクティブは、装飾されていない関数名をエクスポートする必要があり、ビルド構成に応じてエクスポートが異なる場合 (たとえば、32 ビットまたは 64 ビットのビルドで) 便利です。

同じプログラムで 4 つの方法すべてを使用できます。 エクスポートを含むプログラムが LINK によってビルドされる際に、ビルドで .EXP ファイルが使用されていない限り、インポート ライブラリも作成されます。

次に、EXPORTS セクションの例を示します。

```DEF
EXPORTS
   DllCanUnloadNow      @1          PRIVATE
   DllWindowName = WindowName       DATA
   DllGetClassObject    @4 NONAME   PRIVATE
   DllRegisterServer    @7
   DllUnregisterServer
```

.DEF ファイルを使用して DLL から変数をエクスポートする場合、変数に `__declspec(dllexport)` を指定する必要はありません。 ただし、DLL を使用するファイルでは、データの宣言で `__declspec(dllimport)` を引き続き使用する必要があります。

## <a name="see-also"></a>関連項目

[モジュール定義ステートメントに関する規則](rules-for-module-definition-statements.md)
