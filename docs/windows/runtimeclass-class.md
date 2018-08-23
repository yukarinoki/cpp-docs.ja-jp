---
title: RuntimeClass クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::RuntimeClass
dev_langs:
- C++
helpviewer_keywords:
- RuntimeClass class
ms.assetid: d52f9d1a-98e5-41f2-a143-8fb629dd0727
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 8f6cca23834eb889ecb83d91b40861b92fe922ad
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42605985"
---
# <a name="runtimeclass-class"></a>RuntimeClass クラス

指定したインターフェイスを継承し、指定した Windows ランタイム、クラシック COM、および弱い参照のサポートを提供する WinRT または COM クラスを表します。

このクラスの実装を提供する、WinRT と COM クラスの定型実装を提供`QueryInterface`、 `AddRef`、`Release`など、モジュールの参照カウントを管理しのクラス ファクトリを提供するためのサポートアクティブ化可能なオブジェクト。

## <a name="syntax"></a>構文

```cpp
template <typename ...TInterfaces> class RuntimeClass
template <unsigned int classFlags, typename ...TInterfaces> class RuntimeClass;
```

### <a name="parameters"></a>パラメーター

*classFlags*  
省略可能なパラメーター。 1 つ以上を組み合わせた[RuntimeClassType](../windows/runtimeclasstype-enumeration.md)列挙値。 `__WRL_CONFIGURATION_LEGACY__` ClassFlags プロジェクト内のすべてのランタイム クラスの既定値を変更するマクロを定義することができます。 定義されている場合、RuntimeClass インスタンスは既定でアジャイルです。 定義されていないときに、RuntimeClass インスタンスは、既定でアジャイルです。 あいまいさを避けるために指定常に、`Microsoft::WRL::FtmBase`で`TInterfaces`または`RuntimeClassType::InhibitFtmBase`します。 InhibitFtmBase と FtmBase はどちらもオブジェクトを使用している場合は、アジャイルになります。

*TInterfaces*  
インターフェイスの一覧を超えるオブジェクトが実装されて`IUnknown`、`IInspectable`または他のインターフェイスによって制御される[RuntimeClassType](../windows/runtimeclasstype-enumeration.md)します。 特にから派生するその他のクラス リストが`Microsoft::WRL::FtmBase`アジャイル オブジェクトを作成して実装するために、`IMarshal`します。

## <a name="members"></a>メンバー

`RuntimeClassInitialize` 場合、オブジェクトを初期化する関数、`MakeAndInitialize`テンプレート関数は、オブジェクトを構築するために使用します。 初期化に失敗した場合、オブジェクトが正常に初期化すると場合は、S_OK または COM エラー コードを返します。 戻り値として COM エラー コードが伝達される`MakeAndInitialize`します。 なお、`RuntimeClassInitialize`場合、メソッドは呼び出されません、`Make`テンプレート関数は、オブジェクトを構築するために使用します。

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[RuntimeClass::RuntimeClass コンストラクター](../windows/runtimeclass-runtimeclass-constructor.md)|RuntimeClass クラスの現在のインスタンスを初期化します。|
|[RuntimeClass::~RuntimeClass デストラクター](../windows/runtimeclass-tilde-runtimeclass-destructor.md)|RuntimeClass クラスの現在のインスタンスの初期化を解除します。|

## <a name="inheritance-hierarchy"></a>継承階層

これは、実装の詳細です。

## <a name="requirements"></a>要件

**ヘッダー:** implements.h

**名前空間:** Microsoft::WRL

## <a name="see-also"></a>関連項目

[Microsoft::WRL 名前空間](../windows/microsoft-wrl-namespace.md)