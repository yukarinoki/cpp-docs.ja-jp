---
title: リンカー ツールの警告 LNK4049
ms.date: 04/15/2019
f1_keywords:
- LNK4049
helpviewer_keywords:
- LNK4049
ms.assetid: 5fd5fb24-c860-4149-a557-0ac26a65d97c
ms.openlocfilehash: a8e4416eafd47f584de4ab1c83aa7303cab0440a
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80194136"
---
# <a name="linker-tools-warning-lnk4049"></a>リンカー ツールの警告 LNK4049

> '*filename. .obj*' で定義されたシンボル '*symbol*' がインポートされました

シンボルが同じイメージ内のオブジェクトファイル*filename*に定義されているにもかかわらず、*シンボル*に[__declspec (dllimport)](../../cpp/dllexport-dllimport.md)が指定されました。 この警告を解決するには、`__declspec(dllimport)` 修飾子を削除します。

## <a name="remarks"></a>解説

この警告は、1つのオブジェクトファイルにシンボルを定義し、別のオブジェクトで `__declspec(dllimport)` 宣言修飾子を使用して参照すると、リンカーによって生成されます。

Warning LNK4049 は、より一般的なバージョンの[リンカーツールの警告 LNK4217](linker-tools-warning-lnk4217.md)です。 インポートされたシンボルを参照している関数またはオブジェクトファイルを判別できない場合、リンカーは警告 LNK4049 を生成します。

LNK4217 の代わりに LNK4049 が生成される一般的なケースを次に示します。

- [/INCREMENTAL](../../build/reference/incremental-link-incrementally.md)オプションを使用する場合。

- [/Ltcg](../../build/reference/ltcg-link-time-code-generation.md)オプションを使用する場合。

LNK4049 を解決するには、次のいずれかの手順を実行します。

- LNK4049 をトリガーしたシンボルの事前宣言から `__declspec(dllimport)` 修飾子を削除します。 **DUMPBIN**ユーティリティを使用して、バイナリイメージ内のシンボルを検索できます。 **DUMPBIN/SYMBOLS**スイッチは、イメージの COFF シンボルテーブルを表示します。 **Dumpbin**ユーティリティの詳細については、「 [dumpbin Reference](../../build/reference/dumpbin-reference.md)」を参照してください。

- インクリメンタルリンクとプログラム全体の最適化を一時的に無効にします。 再コンパイルすると、アプリケーションによって警告 LNK4217 が生成されます。これには、インポートされたシンボルを参照する関数の名前が含まれます。 インポートされたシンボルから `__declspec(dllimport)` 宣言修飾子を削除し、必要に応じて、インクリメンタルリンクまたはプログラム全体の最適化を再度有効にします。

最終的に生成されたコードは正しく動作しますが、インポートされた関数を呼び出すために生成されるコードは、関数を直接呼び出すよりも効率が悪くなります。 この警告は、 [/clr](../../build/reference/clr-common-language-runtime-compilation.md)オプションを使用してコンパイルした場合には表示されません。

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

2番目のモジュールは、最初のモジュールでエクスポートされた関数への事前宣言を含むオブジェクトファイルを生成し、`main` 関数内でこの関数を呼び出します。 このモジュールを最初のモジュールにリンクすると、LNK4049 が生成されます。 警告を解決するには、`__declspec(dllimport)` 修飾子を宣言から削除します。

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

## <a name="see-also"></a>参照

[リンカーツールの警告 LNK4217](linker-tools-warning-lnk4217.md) \
[リンカーツールの警告 LNK4286](linker-tools-warning-lnk4286.md) \
[dllexport、dllimport](../../cpp/dllexport-dllimport.md)
