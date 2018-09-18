---
title: リンカー ツールの警告 LNK4049 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4049
dev_langs:
- C++
helpviewer_keywords:
- LNK4049
ms.assetid: 5fd5fb24-c860-4149-a557-0ac26a65d97c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3ad4e4adb492789639c71a25a2db774a80cd77c9
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46021760"
---
# <a name="linker-tools-warning-lnk4049"></a>リンカー ツールの警告 LNK4049

ローカルに定義されたシンボル 'symbol' のインポート

シンボルが両方からエクスポートし、プログラムにインポートします。

使用して、シンボルを宣言するときに、この警告がリンカーによって生成された、`__declspec(dllexport)`ストレージ クラス属性の 1 つのオブジェクト ファイルとを使用してそれを参照、`__declspec(dllimport)`別の属性。

警告 LNK4049 は一般的なバージョンの[リンカー ツールの警告 LNK4217](../../error-messages/tool-errors/linker-tools-warning-lnk4217.md)します。 リンカーは、どの関数からインポートされたシンボルが参照された特定できないときに警告 LNK4049 を生成します。

LNK4049 が LNK4217 の代わりに生成される一般的なケースは次のとおりです。

- インクリメンタル リンクを使用して実行する、 [/incremental](../../build/reference/incremental-link-incrementally.md)オプション。

- 使用して、プログラム全体の最適化を実行する、 [/LTCG](../../build/reference/ltcg-link-time-code-generation.md)オプション。

LNK4049 を解決するには、次のいずれかを試してください。

- 削除、 `__declspec(dllimport)` LNK4049 をトリガーしたシンボルの事前宣言から宣言の名前を付けます。 使用してバイナリ イメージ内のシンボルを検索する、 **DUMPBIN**ユーティリティ。 **DUMPBIN/シンボル**スイッチには、イメージの COFF シンボル テーブルが表示されます。 詳細については、 **DUMPBIN**ユーティリティを参照してください[DUMPBIN リファレンス](../../build/reference/dumpbin-reference.md)します。

- インクリメンタル リンクとプログラム全体の最適化を一時的に無効にします。 アプリケーションを再コンパイルすると、インポートされたシンボルの参照元の関数の名前が含まれる警告 LNK4217 が生成されます。 削除、`__declspec(dllimport)`インポートされたシンボルとインクリメンタル リンクの有効化または必要に応じてプログラム全体の最適化から宣言します。

最終的に生成されたコードが正しく動作するが、インポートされた関数の呼び出しに生成されたコードは、関数を直接呼び出すよりも非効率です。 オプションを使用してコンパイルするときに、この警告は表示されません[/clr](../../build/reference/clr-common-language-runtime-compilation.md)します。

詳細については、インポートし、データの宣言をエクスポートを参照してください。 [dllexport、dllimport](../../cpp/dllexport-dllimport.md)します。

## <a name="example"></a>例

次の 2 つのモジュールをリンクすると、LNK4049 が生成されます。 最初のモジュールは、1 つのエクスポートされた関数を含むオブジェクト ファイルを生成します。

```
// LNK4049a.cpp
// compile with: /c

__declspec(dllexport) int func()
{
   return 3;
}
```

## <a name="example"></a>例

2 番目のモジュール内でこの関数を呼び出すと、最初のモジュールでエクスポートされた関数を事前宣言を含むオブジェクト ファイルの生成、`main`関数。 このモジュールを最初のモジュールをリンクすると、LNK4049 が生成されます。 削除、`__declspec(dllimport)`宣言が警告を解決します。

```
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

[リンカー ツールの警告 LNK4217](../../error-messages/tool-errors/linker-tools-warning-lnk4217.md)<br/>
[dllexport、dllimport](../../cpp/dllexport-dllimport.md)