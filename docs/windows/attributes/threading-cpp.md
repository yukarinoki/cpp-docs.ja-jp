---
title: スレッド処理 (C++ COM 属性)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.threading
helpviewer_keywords:
- threading attribute
ms.assetid: 9b558cd6-fbf0-4602-aed5-31c068550ce3
ms.openlocfilehash: 6f83dca442b6508207a4123fa918fc5078bdf664
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88840818"
---
# <a name="threading-c"></a>threading (C++)

COM オブジェクトのスレッド処理モデルを指定します。

## <a name="syntax"></a>構文

```cpp
[ threading(model=enumeration) ]
```

### <a name="parameters"></a>パラメーター

*model*<br/>
Optional次のいずれかのスレッドモデル:

- `apartment` (アパートメントスレッド)

- `neutral` (ユーザーインターフェイスのないコンポーネント .NET Framework)

- `single` (単純なスレッド処理)

- `free` (フリースレッド)

- `both` (アパートメントおよびフリースレッド)

既定値は `apartment` です。

## <a name="remarks"></a>Remarks

**スレッド**化 C++ 属性は、生成された .idl ファイルには表示されませんが、COM オブジェクトの実装で使用されます。

ATL プロジェクトでは、 [coclass](coclass.md) 属性も存在する場合、 *モデル* で指定されたスレッドモデルは、属性によって挿入される [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md) クラスにテンプレートパラメーターとして渡され `coclass` ます。

**スレッド**属性は、 [event_source](event-source.md)へのアクセスも保護します。

## <a name="example"></a>例

**スレッド処理**の使用例については、[ライセンス](licensed.md)の例を参照してください。

## <a name="requirements"></a>必要条件

| 属性コンテキスト | 値 |
|-|-|
|**適用対象**|**`class`**, **`struct`**|
|**Repeatable**|いいえ|
|**必須属性**|**coclass**|
|**無効な属性**|なし|

属性コンテキストの詳細については、「 [属性コンテキスト](cpp-attributes-com-net.md#contexts)」を参照してください。

## <a name="see-also"></a>関連項目

[COM 属性](com-attributes.md)<br/>
[Typedef、Enum、Union、および Struct 属性](typedef-enum-union-and-struct-attributes.md)<br/>
[クラス属性](class-attributes.md)<br/>
[旧形式のコードのためのマルチスレッド サポート (Visual C++)](../../parallel/multithreading-support-for-older-code-visual-cpp.md)<br/>
[ニュートラルアパートメント](/windows/win32/cossdk/neutral-apartments)
