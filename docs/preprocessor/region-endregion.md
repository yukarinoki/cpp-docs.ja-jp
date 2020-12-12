---
description: '詳細情報: region、endregion プラグマ'
title: region プラグマ、endregion プラグマ
ms.date: 08/29/2019
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
ms.openlocfilehash: a12305240f0c05913d16c5f26fb64661fc08e736
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97167423"
---
# <a name="region-endregion-pragmas"></a>region プラグマ、endregion プラグマ

`#pragma region` Visual Studio Code エディターの [アウトライン機能](/visualstudio/ide/outlining) を使用して展開または折りたたむことができるコードブロックを指定できます。

## <a name="syntax"></a>構文

> **#pragma リージョン** *名前*\
> **#pragma endregion** *コメント*

### <a name="parameters"></a>パラメーター

*関する*\
Optionalコードエディターに表示するコメント。

*指定*\
Optional領域の名前。 この名前はコードエディターに表示されます。

## <a name="remarks"></a>解説

`#pragma endregion` ブロックの終了をマーク `#pragma region` します。

ブロックは、 `#region` ディレクティブで終了する必要があり `#pragma endregion` ます。

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

[プラグマ ディレクティブと __pragma キーワード](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
