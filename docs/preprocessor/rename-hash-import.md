---
title: 名前の変更 (#import)
ms.date: 10/18/2018
f1_keywords:
- Rename
helpviewer_keywords:
- rename attribute
ms.assetid: 5c5c6153-1087-4b7b-87fb-fc59b90b9975
ms.openlocfilehash: 15673a8b9ebaf298ae1b2b45c9a76a1691e681b1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50514193"
---
# <a name="rename-import"></a>名前を変更 (\#インポート)

**C++ 固有の仕様**

名前の衝突の問題を回避します。

## <a name="syntax"></a>構文

```
rename("OldName","NewName")
```

### <a name="parameters"></a>パラメーター

*OldName*<br/>
タイプ ライブラリ内の古い名前。

*NewName*<br/>
古い名前の代わりに使用する名前。

## <a name="remarks"></a>Remarks

この属性が指定されている場合、コンパイラはのすべての出現箇所に置き換えます*OldName*を持つユーザーが指定したタイプ ライブラリで*NewName*結果のヘッダー ファイルでします。

この属性は、タイプ ライブラリ内の名前がシステム ヘッダー ファイル内のマクロ定義と一致する場合に使用できます。 このような状況が解決されないかどうかは、さまざまな構文エラーが生成されますなど[コンパイラ エラー C2059](../error-messages/compiler-errors-1/compiler-error-c2059.md)と[コンパイラ エラー C2061](../error-messages/compiler-errors-1/compiler-error-c2061.md)します。

> [!NOTE]
> 置換は、結果のヘッダー ファイルで使用される名前ではなく、タイプ ライブラリで使用される名前に対して実行されます。

たとえば `MyParent` という名前のプロパティがタイプ ライブラリにあり、マクロ `GetMyParent` がヘッダー ファイルに定義され、`#import` の前で使用されているとします。 `GetMyParent`エラー処理ラッパー関数の既定の名前は、`get`プロパティ、名前の競合が発生します。 問題を回避するには、`#import` ステートメント内で次の属性を使用します。

```cpp
rename("MyParent","MyParentX")
```

これにより、タイプ ライブラリ内の `MyParent` の名前が変更されます。 `GetMyParent` ラッパーの名前を変更しようとすると、失敗します:

```cpp
rename("GetMyParent","GetMyParentX")
```

これは、名前 `GetMyParent` が、結果のタイプ ライブラリ ヘッダー ファイルにのみ出現するためです。

**END C 固有の仕様**

## <a name="see-also"></a>関連項目

[#import の属性](../preprocessor/hash-import-attributes-cpp.md)<br/>
[#import ディレクティブ](../preprocessor/hash-import-directive-cpp.md)