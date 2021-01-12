---
description: '詳細情報: &lt; 戻り値&gt;'
title: '&lt;> を返します (C++ ドキュメントコメント)'
ms.date: 11/04/2016
f1_keywords:
- <returns>
helpviewer_keywords:
- returns C++ XML tag
- <returns> C++ XML tag
ms.assetid: 5e3b0ed9-838d-4953-a93e-76d2d0a19fb9
ms.openlocfilehash: 59b9a7d33a3b2695a2a5e22fdac465f17c915492
ms.sourcegitcommit: 118e4ad82c0f1c9ac120f105d84224e5fe4cef28
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "98126118"
---
# <a name="ltreturnsgt"></a>&lt;returns&gt;

\<returns> タグは、戻り値を説明するためにメソッドの宣言のコメントで使用する必要があります。

## <a name="syntax"></a>構文

```
<returns>description</returns>
```

#### <a name="parameters"></a>パラメーター

*description*<br/>
戻り値の説明。

## <a name="remarks"></a>Remarks

ドキュメントコメントをファイルに処理するために、 [/doc](doc-process-documentation-comments-c-cpp.md) を使用してコンパイルします。

## <a name="example"></a>例

```cpp
// xml_returns_tag.cpp
// compile with: /LD /clr /doc
// post-build command: xdcmake xml_returns_tag.dll

/// Text for class MyClass.
public ref class MyClass {
public:
   /// <returns>Returns zero.</returns>
   int GetZero() { return 0; }
};
```

## <a name="see-also"></a>関連項目

[XML に関するドキュメント](xml-documentation-visual-cpp.md)
