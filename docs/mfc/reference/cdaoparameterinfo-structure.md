---
title: CDaoParameterInfo 構造体
ms.date: 09/17/2019
f1_keywords:
- CDaoParameterInfo
helpviewer_keywords:
- CDaoParameterInfo structure [MFC]
- DAO (Data Access Objects), Parameters collection
ms.assetid: 45fd53cd-cb84-4e12-b48d-7f2979f898ad
ms.openlocfilehash: 6d594bbeec34e400eb074c136e3467e78b35c4ee
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368982"
---
# <a name="cdaoparameterinfo-structure"></a>CDaoParameterInfo 構造体

構造体`CDaoParameterInfo`には、データ アクセス オブジェクト (DAO) に定義されたパラメーター オブジェクトに関する情報が含まれています。 DAO 3.6 は最終バージョンであり、廃止と見なされます。

## <a name="syntax"></a>構文

```
struct CDaoParameterInfo
{
    CString m_strName;       // Primary
    short m_nType;           // Primary
    ColeVariant m_varValue;  // Secondary
};
```

#### <a name="parameters"></a>パラメーター

*m_strName*<br/>
パラメータ オブジェクトに一意の名前を付けます。 詳細については、DAO ヘルプの「プロパティ名」を参照してください。

*m_nType*<br/>
パラメーター オブジェクトのデータ型を示す値。 使用可能な値のリストについては[、CDaoFieldInfo](../../mfc/reference/cdaofieldinfo-structure.md)構造体の*m_nType*メンバーを参照してください。 詳細については、DAO ヘルプの「型プロパティ」を参照してください。

*m_varValue*<br/>
[オブジェクトに](../../mfc/reference/colevariant-class.md)格納されているパラメーターの値。

## <a name="remarks"></a>解説

上のプライマリおよびセカンダリへの参照は、クラス`CDaoQueryDef`の[GetParameterInfo](../../mfc/reference/cdaoquerydef-class.md#getparameterinfo)メンバー関数によって情報がどのように返されるか示しています。

MFC では、DAO パラメータ オブジェクトはクラスにカプセル化されません。 MFC`CDaoQueryDef`オブジェクトの基になる DAO クエリ定義オブジェクトは、パラメーターをパラメーター コレクションに格納します。 [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md)オブジェクト内のパラメーター オブジェクトにアクセスするには、特定のパラメーター名に`GetParameterInfo`対するクエリ定義オブジェクトのメンバー関数を呼び出すか、または Parameters コレクションのインデックスを呼び出します。 [メンバー関数](../../mfc/reference/cdaoquerydef-class.md#getparametercount)を使用して、パラメーター コレクション`GetParameterInfo`をループできます。

メンバー[関数によって取得](../../mfc/reference/cdaoquerydef-class.md#getparameterinfo)される情報は、`CDaoParameterInfo`構造体に格納されます。 パラメーター`GetParameterInfo`オブジェクトが格納されている Parameters コレクション内の querydef オブジェクトを呼び出します。

> [!NOTE]
> パラメーターの値のみを取得または設定する場合は、クラス`CDaoRecordset`の[GetParamValue および SetParamValue](../../mfc/reference/cdaorecordset-class.md#getparamvalue)メンバー関数を使用します。 [SetParamValue](../../mfc/reference/cdaorecordset-class.md#setparamvalue)

`CDaoParameterInfo`また、デバッグ`Dump`ビルドでメンバー関数を定義します。 を使用`Dump`して、オブジェクトの内容を`CDaoParameterInfo`ダンプできます。

## <a name="requirements"></a>必要条件

**ヘッダー:** afxdao.h

## <a name="see-also"></a>関連項目

[構造体、スタイル、コールバック関数とメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[クラス](../../mfc/reference/cdaoquerydef-class.md)
