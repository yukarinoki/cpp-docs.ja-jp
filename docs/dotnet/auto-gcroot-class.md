---
title: auto_gcroot クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- msclr::auto_gcroot
- msclr.auto_gcroot
- auto_gcroot
dev_langs:
- C++
helpviewer_keywords:
- auto_gcroot
ms.assetid: b5790912-265d-463e-a486-47302e91042a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 48412a932ff3752b0613f7045cd88992332b7917
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46423230"
---
# <a name="autogcroot-class"></a>auto_gcroot クラス

自動リソース管理 (など[auto_ptr クラス](../standard-library/auto-ptr-class.md)) ネイティブ型に仮想のハンドルを埋め込むために使用できます。

## <a name="syntax"></a>構文

```cpp
template<typename _element_type>
class auto_gcroot;
```

#### <a name="parameters"></a>パラメーター

*_element_type*<br/>
埋め込みのマネージ型。

## <a name="requirements"></a>要件

**ヘッダー ファイル** \<msclr\auto_gcroot.h >

**Namespace** msclr

## <a name="see-also"></a>関連項目

[auto_gcroot](../dotnet/auto-gcroot.md)<br/>
[auto_gcroot のメンバー](../dotnet/auto-gcroot-members.md)<br/>
[方法: ネイティブ型のハンドルを宣言する](../dotnet/how-to-declare-handles-in-native-types.md)<br/>
[auto_handle クラス](../dotnet/auto-handle-class.md)