---
title: '&lt;remarks > (ドキュメント コメントの C++)'
ms.date: 11/04/2016
f1_keywords:
- remarks
- <remarks>
helpviewer_keywords:
- <remarks> C++ XML tag
- remarks C++ XML tag
ms.assetid: c820083b-3192-40ab-9ec8-1472c55b4247
ms.openlocfilehash: 0d0c63d55de80f498498a6873dacb5e83fc956b7
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2019
ms.locfileid: "57827178"
---
# <a name="ltremarksgt"></a>&lt;remarks&gt;

\<remarks> タグを使用して、型の情報を追加し、[\<summary>](summary-visual-cpp.md) で指定された情報を補足します。 この情報は[オブジェクト ブラウザー](/visualstudio/ide/viewing-the-structure-of-code)とコード コメント Web レポートに表示されます。

## <a name="syntax"></a>構文

```
<remarks>description</remarks>
```

#### <a name="parameters"></a>パラメーター

*description*<br/>
メンバーの説明。

## <a name="remarks"></a>Remarks

コンパイル時に [/doc](doc-process-documentation-comments-c-cpp.md) を指定して、ドキュメント コメントをファイルに出力します。

## <a name="example"></a>例

```
// xml_remarks_tag.cpp
// compile with: /LD /clr /doc
// post-build command: xdcmake xml_remarks_tag.dll

using namespace System;

/// <summary>
/// You may have some primary information about this class.
/// </summary>
/// <remarks>
/// You may have some additional information about this class.
/// </remarks>
public ref class MyClass {};
```

## <a name="see-also"></a>関連項目

[XML に関するドキュメント](xml-documentation-visual-cpp.md)
