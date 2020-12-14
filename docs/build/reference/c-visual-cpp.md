---
description: '詳細情報: &lt; c&gt;'
title: '&lt;c> (C++ ドキュメントコメント)'
ms.date: 11/04/2016
f1_keywords:
- <c>
helpviewer_keywords:
- <c> C++ XML tag
- c C++ XML tag
ms.assetid: 3b23fc0f-e10d-4dd0-b197-48a46cbddd9f
ms.openlocfilehash: 35d06183136a82c602b5e4daa288fb4518962154
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97182620"
---
# <a name="ltcgt"></a>&lt;c&gt;

タグは、 \<c> 説明内のテキストをコードとしてマークする必要があることを示します。 複数行をコードとして示す場合は、[\<code>](code-visual-cpp.md) を使用します。

## <a name="syntax"></a>構文

```
<c>text</c>
```

#### <a name="parameters"></a>パラメーター

*text*<br/>
コードとして示すテキストです。

## <a name="remarks"></a>解説

ドキュメントコメントをファイルに処理するために、 [/doc](doc-process-documentation-comments-c-cpp.md) を使用してコンパイルします。

## <a name="example"></a>例

```cpp
// xml_c_tag.cpp
// compile with: /doc /LD
// post-build command: xdcmake xml_c_tag.xdc

/// Text for class MyClass.
class MyClass {
public:
   int m_i;
   MyClass() : m_i(0) {}

   /// <summary><c>MyMethod</c> is a method in the <c>MyClass</c> class.
   /// </summary>
   int MyMethod(MyClass * a) {
      return a -> m_i;
   }
};
```

## <a name="see-also"></a>関連項目

[XML に関するドキュメント](xml-documentation-visual-cpp.md)
