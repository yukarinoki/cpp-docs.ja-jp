---
description: '詳細情報: importlib'
title: importlib (C++ COM 属性)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.importlib
helpviewer_keywords:
- importlib attribute
ms.assetid: f129e459-b8d3-4aca-a0bc-ee53e18b62ed
ms.openlocfilehash: f3000be3415ed944d621ebcd36442e33951efc84
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97114950"
---
# <a name="importlib"></a>importlib

既に他のタイプ ライブラリでコンパイル済みの型を、作成中のタイプ ライブラリで使用できるようにします。

## <a name="syntax"></a>構文

```cpp
[ importlib("tlb_file") ];
```

### <a name="parameters"></a>パラメーター

*tlb_file*<br/>
現在のプロジェクトのタイプ ライブラリにインポートする .tlb ファイルの名前 (引用符で囲む)。

## <a name="remarks"></a>解説

**Importlib** C++ 属性により、 `importlib` 生成された .idl ファイルのライブラリブロックにステートメントが配置されます。 **Importlib** 属性には、 [importlib](/windows/win32/Midl/importlib) MIDL 属性と同じ機能があります。

## <a name="example"></a>例

次のコードは、 **importlib** の使用方法の例を示しています。

```cpp
// cpp_attr_ref_importlib.cpp
// compile with: /LD
[module(name="MyLib")];
[importlib("importlib.tlb")];
```

## <a name="requirements"></a>要件

| 属性コンテキスト | 値 |
|-|-|
|**適用対象**|任意の場所|
|**Repeatable**|いいえ|
|**必須属性**|なし|
|**無効な属性**|なし|

詳細については、「 [属性コンテキスト](cpp-attributes-com-net.md#contexts)」を参照してください。

## <a name="see-also"></a>関連項目

[コンパイラ属性](compiler-attributes.md)<br/>
[スタンドアロン属性](stand-alone-attributes.md)<br/>
[import](import.md)<br/>
[importidl](importidl.md)<br/>
[用意](include-cpp.md)<br/>
[includelib](includelib-cpp.md)
