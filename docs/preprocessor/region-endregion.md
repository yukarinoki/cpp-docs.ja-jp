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
ms.openlocfilehash: c73a90aa2be83d643b74dde4645081e89da3ff73
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62179751"
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