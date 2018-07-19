---
title: RuntimeClass クラス |Microsoft ドキュメント
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
ms.openlocfilehash: 26c3542f5bea21d1b705cd3253e6828ff73677df
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33889008"
---
# <a name="runtimeclass-class"></a>RuntimeClass クラス
指定されたインターフェイスを継承し、指定した Windows ランタイム、クラシック COM、および弱い参照のサポートを提供する WinRT または COM クラスを表します。  
  
このクラスの実装を提供する、WinRT と COM クラスのスケルトンの実装を提供`QueryInterface`、 `AddRef`、`Release`など、モジュールの参照カウントを管理し、用のクラス ファクトリを提供するためのサポートアクティブ化可能なオブジェクトです。
  
## <a name="syntax"></a>構文  
  
```
template <typename ...TInterfaces> class RuntimeClass
template <unsigned int classFlags, typename ...TInterfaces> class RuntimeClass;
```
  
#### <a name="parameters"></a>パラメーター  
 `classFlags`  
省略可能なパラメーターです。 1 つまたは複数の組み合わせ[RuntimeClassType](../windows/runtimeclasstype-enumeration.md)列挙値。 `__WRL_CONFIGURATION_LEGACY__` ClassFlags プロジェクト内のすべてのランタイム クラスの既定値を変更するマクロを定義することができます。 定義されている場合は RuntimeClass インスタンスは既定でアジャイルです。 定義されていない場合、RuntimeClass インスタンスは、既定でアジャイルです。 避けるためにあいまいさが常に指定の Microsoft::WRL::FtmBase`TInterfaces`または RuntimeClassType::InhibitFtmBase です。 注、InhibitFtmBase と FtmBase が両方のオブジェクトを使用する場合はアジャイルになります。
 
 `TInterfaces`  
IUnknown、IInspectable またはその他のインターフェイスによって制御されるを超えてインターフェイスのリスト オブジェクトに実装されて[RuntimeClassType](../windows/runtimeclasstype-enumeration.md)です。 オブジェクトをアジャイルにして、IMarshal を実装するために、特に Microsoft::WRL::FtmBase から派生させるのには、他のクラスを一覧に可能性がありますもします。
  
## <a name="members"></a>メンバー  
`RuntimeClassInitialize` MakeAndInitialize テンプレート関数は、オブジェクトを構築するために使用する場合は、オブジェクトを初期化する関数。 初期化に失敗した場合、オブジェクトが正常に初期化されている場合は S_OK、または COM エラー コードを返します。 COM エラー コードは、MakeAndInitialize の戻り値として伝達されます。 Make テンプレート関数が、オブジェクトを構築するために使用する場合に、RuntimeClassInitialize メソッドが呼び出されないことに注意してください。

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
