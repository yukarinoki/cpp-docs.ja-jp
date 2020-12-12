---
description: 詳細については、「リンカーツールの警告 LNK4049」を参照してください。
title: リンカー ツールの警告 LNK4049
ms.date: 04/15/2019
f1_keywords:
- LNK4049
helpviewer_keywords:
- LNK4049
ms.assetid: 5fd5fb24-c860-4149-a557-0ac26a65d97c
ms.openlocfilehash: 2451c5533b22eacb0b640ed301203f6332b6681d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97210323"
---
# <a name="linker-tools-warning-lnk4049"></a>リンカー ツールの警告 LNK4049

> '*filename. .obj*' で定義されたシンボル '*symbol*' がインポートされました

シンボルが同じイメージ内のオブジェクトファイル *filename* に定義されているにもかかわらず、*シンボル* に [__declspec (dllimport)](../../cpp/dllexport-dllimport.md)が指定されました。 `__declspec(dllimport)`この警告を解決するには、修飾子を削除します。

## <a name="remarks"></a>解説

この警告は、1つのオブジェクトファイルにシンボルを定義し、別のオブジェクトで宣言修飾子を使用して参照すると、リンカーによって生成され `__declspec(dllimport)` ます。

Warning LNK4049 は、より一般的なバージョンの [リンカーツールの警告 LNK4217](linker-tools-warning-lnk4217.md)です。 インポートされたシンボルを参照している関数またはオブジェクトファイルを判別できない場合、リンカーは警告 LNK4049 を生成します。

LNK4217 の代わりに LNK4049 が生成される一般的なケースを次に示します。

- [/INCREMENTAL](../../build/reference/incremental-link-incrementally.md)オプションを使用する場合。

- [/Ltcg](../../build/reference/ltcg-link-time-code-generation.md)オプションを使用する場合。

LNK4049 を解決するには、次のいずれかの手順を実行します。

- LNK4049 を `__declspec(dllimport)` トリガーしたシンボルの事前宣言から修飾子を削除します。 **DUMPBIN** ユーティリティを使用して、バイナリイメージ内のシンボルを検索できます。 **DUMPBIN/SYMBOLS** スイッチは、イメージの COFF シンボルテーブルを表示します。 **Dumpbin** ユーティリティの詳細については、「 [dumpbin Reference](../../build/reference/dumpbin-reference.md)」を参照してください。

- インクリメンタルリンクとプログラム全体の最適化を一時的に無効にします。 再コンパイルすると、アプリケーションによって警告 LNK4217 が生成されます。これには、インポートされたシンボルを参照する関数の名前が含まれます。 インポートされ `__declspec(dllimport)` たシンボルから宣言修飾子を削除し、必要に応じて、インクリメンタルリンクまたはプログラム全体の最適化を再度有効にします。

最終的に生成されたコードは正しく動作しますが、インポートされた関数を呼び出すために生成されるコードは、関数を直接呼び出すよりも効率が悪くなります。 この警告は、 [/clr](../../build/reference/clr-common-language-runtime-compilation.md) オプションを使用してコンパイルした場合には表示されません。

データのインポートとエクスポートの宣言の詳細については、「 [dllexport、dllimport](../../cpp/dllexport-dllimport.md)」を参照してください。

## <a name="example"></a>例

次の2つのモジュールをリンクすると、LNK4049 が生成されます。 最初のモジュールは、1つのエクスポートされた関数を含むオブジェクトファイルを生成します。

```cpp
// LNK4049a.cpp
// compile with: /c

__declspec(dllexport) int func()
{
   return 3;
}
```

2番目のモジュールは、最初のモジュールでエクスポートされた関数への事前宣言を含むオブジェクトファイルと、関数内でのこの関数の呼び出しを生成し `main` ます。 このモジュールを最初のモジュールにリンクすると、LNK4049 が生成されます。 警告を `__declspec(dllimport)` 解決するには、修飾子を宣言から削除します。

```cpp
// LNK4049b.cpp
// compile with: /link /WX /LTCG LNK4049a.obj
// LNK4049 expected

__declspec(dllimport) int func();
// try the following line instead
// int func();

int main()
{
   return func();
}
```

## <a name="see-also"></a>関連項目

[リンカーツールの警告 LNK4217](linker-tools-warning-lnk4217.md) \
[リンカーツールの警告 LNK4286](linker-tools-warning-lnk4286.md) \
[dllexport、dllimport](../../cpp/dllexport-dllimport.md)
