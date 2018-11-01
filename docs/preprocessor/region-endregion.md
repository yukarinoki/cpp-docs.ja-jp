---
title: region、endregion
ms.date: 10/18/2018
f1_keywords:
- vc-pragma.endregion
- endregion_CPP
- region_CPP
- vc-pragma.region
helpviewer_keywords:
- pragmas, region
- pragmas, endregion
- endregion pragma
- region pragma
ms.assetid: c697f807-622f-4796-851b-68a42bbecd84
ms.openlocfilehash: efc5f9c09449ff2fefff41261fe8b0eb0be80278
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50512795"
---
# <a name="region-endregion"></a>region、endregion

`#pragma region` 展開したり折りたたむを使用する場合のコードのブロックを指定することができます、[アウトライン機能](/visualstudio/ide/outlining)の Visual Studio コード エディター。

## <a name="syntax"></a>構文

```
#pragma region name
#pragma endregion comment
```

### <a name="parameters"></a>パラメーター

*comment*<br/>
(省略可能)コード エディターに表示されるコメントです。

*name*<br/>
(省略可能)領域の名前。  この名前はコード エディターに表示されます。

## <a name="remarks"></a>Remarks

`#pragma endregion` 末尾を`#pragma region`ブロックします。

A`#region`でブロックを終了する必要があります`#pragma endregion`します。

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

[プラグマ ディレクティブと __Pragma キーワード](../preprocessor/pragma-directives-and-the-pragma-keyword.md)