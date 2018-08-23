---
title: HString クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HString
dev_langs:
- C++
ms.assetid: 6709dd2e-8d72-4675-8ec7-1baa7d71854d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: eea40f989e7d41afbff2773fcc5e6e5b2cfbafd2
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42613654"
---
# <a name="hstring-class"></a>HString クラス

RAII パターンを使用して、HSTRING の有効期間を管理するためのヘルパー クラスです。

## <a name="syntax"></a>構文

```cpp
class HString;
```

## <a name="remarks"></a>Remarks

Windows ランタイムでは、HSTRING ハンドルを使用して文字列へのアクセスを提供します。 **HString**クラスには、便利な関数および HSTRING ハンドルの使用を簡単に演算子が用意されています。 このクラスは、RAII パターンを所有している HSTRING の有効期間を処理できます。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[HString::HString コンストラクター](../windows/hstring-hstring-constructor.md)|新しいインスタンスを初期化、 **HString**クラス。|
|[HString::~HString デストラクター](../windows/hstring-tilde-hstring-destructor.md)|現在のインスタンスを破棄、 **HString**クラス。|

### <a name="members"></a>メンバー

|名前|説明|
|----------|-----------------|
|[HString::Set メソッド](../windows/hstring-set-method.md)|現在の値を設定**HString**ワイド文字の文字列を指定するオブジェクトまたは**HString**パラメーター。|
|[HString::Attach メソッド](../windows/hstring-attach-method.md)|指定した関連付けます**HString**オブジェクトと現在**HString**オブジェクト。|
|[HString::CopyTo メソッド](../windows/hstring-copyto-method.md)|現在のコピー **HString**オブジェクトを HSTRING オブジェクトにします。|
|[HString::Detach メソッド](../windows/hstring-detach-method.md)|指定された関連付けを解除**HString**その基になる値からオブジェクトです。|
|[HString::GetAddressOf メソッド](../windows/hstring-getaddressof-method.md)|基になる HSTRING ハンドルへのポインターを取得します。|
|[HString::Get メソッド](../windows/hstring-get-method.md)|基になる HSTRING ハンドルの値を取得します。|
|[HString::Release メソッド](../windows/hstring-release-method.md)|基になる文字列値を削除し、現在を初期化します。 **HString**オブジェクトから空の値。|
|[HString::MakeReference メソッド](../windows/hstring-makereference-method.md)|作成、`HStringReference`オブジェクト指定した文字列パラメーターから。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[HString::Operator= 演算子](../windows/hstring-operator-assign-operator.md)|別の値を移動**HString**現在オブジェクト**HString**オブジェクト。|
|[HString::Operator== 演算子](../windows/hstring-operator-equality-operator.md)|2 つのパラメーターが等しいかどうかを示します。|
|[HString::Operator!= 演算子](../windows/hstring-operator-inequality-operator.md)|2 つのパラメーターが異なるかどうかを示します。|

## <a name="inheritance-hierarchy"></a>継承階層

`HString`

## <a name="requirements"></a>要件

**ヘッダー:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers

## <a name="see-also"></a>関連項目

[Microsoft::WRL::Wrappers 名前空間](../windows/microsoft-wrl-wrappers-namespace.md)