---
title: エクスポート |Microsoft Docs
ms.custom: ''
ms.date: 09/07/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- EXPORTS
dev_langs:
- C++
helpviewer_keywords:
- EXPORTS .def file statement
ms.assetid: dbcd7579-b855-44c4-bd27-931e157657f7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6bf350b0a129c642678fc6af1bac7d35633fe909
ms.sourcegitcommit: 997e6b7d336cddb388bb6e9e56527725fcaa0624
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/08/2018
ms.locfileid: "48860980"
---
# <a name="exports"></a>EXPORTS

関数またはデータのエクスポート名または序数を指定する 1 つ以上のエクスポート定義のセクションを導入します。 各定義は個別の行に指定する必要があります。

```DEF
EXPORTS
   definition
```

## <a name="remarks"></a>Remarks

最初の*定義*と同じ行に配置できる、`EXPORTS`キーワードまたは後続の行にします。 .DEF ファイルには、1 つ以上の `EXPORTS` ステートメントを含めることができます。

エクスポートの構文は、*定義*は。

> *entryname*\[__=__*internal_name*|*other_module.exported_name*] \[**\@**_序数_ \[ **NONAME**] \[ \[**プライベート**] |\[**データ**]

*entryname*にエクスポートする関数または変数の名前です。 これは必須です。 DLL の名前からエクスポートする名前が異なる場合、エクスポートの名前、DLL を使用して指定*internal_name*します。 たとえば、DLL で関数 `func1` をエクスポートし、呼び出し元がそれを `func2` として使用する場合は、次のように指定します。

```DEF
EXPORTS
   func2=func1
```

エクスポートする名前が他のいくつかのモジュールからの場合は、エクスポートの名前、DLL を使用して指定*other_module.exported_name*します。 たとえば、DLL で関数 `other_module.func1` をエクスポートし、呼び出し元がそれを `func2` として使用する場合は、次のように指定します。

```DEF
EXPORTS
   func2=other_module.func1
```

序数でエクスポートする別のモジュールからエクスポートする名前がある場合の指定を使用して、エクスポートの DLL で序数に基づく*other_module*.__#__ *序数*します。 たとえば、DLL から他のモジュールでは序数の 42 し、呼び出し元として使用する関数のエクスポート`func2`、指定します。

```DEF
EXPORTS
   func2=other_module.#42
```

装飾名を使用する必要がありますか、Visual C コンパイラでは、C++ の関数に名前の装飾を使用しているため、 *internal_name*を使用して、エクスポートされた関数を定義または`extern "C"`ソース コードにします。 コンパイラを使用する C 関数を装飾も、 [_ _stdcall](../../cpp/stdcall.md)呼び出し規約をアンダー スコア (\_) のプレフィックスとサフィックスで構成される、アット マーク (\@) (10 進数) のバイト数の後に、引数リスト。

コンパイラによって生成された装飾名を検索するには、使用、 [DUMPBIN](../../build/reference/dumpbin-reference.md)ツールまたはリンカー [/map](../../build/reference/map-generate-mapfile.md)オプション。 装飾名はコンパイラ固有です。 装飾名を .DEF ファイルにエクスポートする場合、DLL にリンクする実行可能ファイルも同じバージョンのコンパイラを使用してビルドする必要があります。 これにより、呼び出し元の装飾名は .DEF ファイルのエクスポート名と一致します。

使用することができます\@*序数*数値、および関数名ではなくが DLL のエクスポート テーブルに移動を指定します。 多くの Windows DLL で、レガシ コードをサポートするために序数がエクスポートされます。 DLL のサイズを最小限に抑えるのに役立つため、16 ビットの Windows コードでは序数を使用することが一般的でした。 レガシ サポートのために DLL のクライアントで必要な場合を除き、関数を序数でエクスポートすることはお勧めしません。 .LIB ファイルには序数と関数のマッピングが含まれているため、DLL を使用するプロジェクトでは通常と同様に関数名を使用できます。

オプションを使用して**NONAME**キーワード、序数のみをエクスポートし、結果の DLL のエクスポート テーブルのサイズを小さくことができます。 ただし、使用する場合[GetProcAddress](https://msdn.microsoft.com/library/windows/desktop/ms683212.aspx) DLL の名前を有効にすることはできないために、序数を知る必要があります。

省略可能なキーワード**プライベート**防止*entryname* LINK によって生成されるインポート ライブラリに含まれるからです。 同じく LINK によって生成されるイメージ内のエクスポートには影響しません。

省略可能なキーワード**データ**エクスポートがコードではなく、データを指定します。 次の例では、`exported_global` という名前のデータ変数をエクスポートする方法を示します。

```DEF
EXPORTS
   exported_global DATA
```

定義をエクスポートするには 4 つの方法があり、それらを推奨される順序で示します。

1. [方式](../../cpp/dllexport-dllimport.md)ソース コード内のキーワード

1. .DEF ファイルでの `EXPORTS` ステートメント

1. [/Export](../../build/reference/export-exports-a-function.md) LINK コマンド内の指定

1. A[コメント](../../preprocessor/comment-c-cpp.md)形式のソース コードにディレクティブ`#pragma comment(linker, "/export: definition ")`します。 次の例は、関数宣言の前に、の #pragma comment ディレクティブ、`PlainFuncName`非装飾の名前と`_PlainFuncName@4`関数の装飾の名前を指定します。

    ```cpp
    #pragma comment(linker, "/export:PlainFuncName=_PlainFuncName@4")
    BOOL CALLBACK PlainFuncName( Things * lpParams)
    ```

#Pragma ディレクティブは、(たとえば、32 ビットまたは 64 ビットのビルド) でビルド構成によっては別のエクスポートをして、装飾されていない関数の名前をエクスポートする必要がある場合に便利です。

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

[モジュール定義ステートメントに関する規則](../../build/reference/rules-for-module-definition-statements.md)
