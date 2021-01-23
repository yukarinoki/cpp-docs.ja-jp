---
description: pragmaMicrosoft C/c + + での region および endregion ディレクティブの詳細については、こちらを参照してください。
title: region および endregion pragma
ms.date: 01/22/2021
f1_keywords:
- vc-pragma.endregion
- endregion_CPP
- region_CPP
- vc-pragma.region
helpviewer_keywords:
- pragma, region
- pragma, endregion
- endregion pragma
- region pragma
no-loc:
- pragma
ms.openlocfilehash: 68964cd2cab4ff344a8319f970f7ee94be4d378d
ms.sourcegitcommit: a26a66a3cf479e0e827d549a9b850fad99b108d1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "98713286"
---
# <a name="region-and-endregion-no-locpragma"></a>`region` および `endregion` pragma

`#pragma region` Visual Studio エディターの [アウトライン機能](/visualstudio/ide/outlining) を使用して、展開または折りたたむことができるコードブロックを指定できます。

## <a name="syntax"></a>構文

> **`#pragma region`***名前*\
> **`#pragma endregion`***コメント*

### <a name="parameters"></a>パラメーター

*関する*\
Optionalコードエディターに表示するコメント。

*指定*\
Optional領域の名前。 この名前はコードエディターに表示されます。

## <a name="remarks"></a>解説

`#pragma endregion` ブロックの終了をマーク `#pragma region` します。

ブロックは、 `#pragma region` ディレクティブで終了する必要があり `#pragma endregion` ます。

## <a name="example"></a>例

```cpp
// pragma_directives_region.cpp
#pragma region Region_1
void Test() {}
void Test2() {}
void Test3() {}
#pragma endregion Region_1

int main() {}
```

## <a name="see-also"></a>関連項目

[プラグマディレクティブと `__pragma` `_Pragma` キーワードおよびキーワード](./pragma-directives-and-the-pragma-keyword.md)
