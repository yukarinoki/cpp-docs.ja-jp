---
description: '詳細については、次を参照してください: CDaoParameterInfo 構造体'
title: CDaoParameterInfo 構造体
ms.date: 09/17/2019
f1_keywords:
- CDaoParameterInfo
helpviewer_keywords:
- CDaoParameterInfo structure [MFC]
- DAO (Data Access Objects), Parameters collection
ms.assetid: 45fd53cd-cb84-4e12-b48d-7f2979f898ad
ms.openlocfilehash: b4cd1916bb30c3b646e9b0892e2bdcdf5ade30b4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97250721"
---
# <a name="cdaoparameterinfo-structure"></a>CDaoParameterInfo 構造体

構造体には、 `CDaoParameterInfo` データアクセスオブジェクト (DAO) 用に定義されたパラメーターオブジェクトに関する情報が含まれています。 DAO 3.6 は最終バージョンであり、互換性のために残されているものと見なされます。

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
パラメーターオブジェクトに一意の名前を指定します。 詳細については、DAO ヘルプの「Name プロパティ」を参照してください。

*m_nType*<br/>
パラメーターオブジェクトのデータ型を示す値です。 使用可能な値の一覧については、 [CDaoFieldInfo](../../mfc/reference/cdaofieldinfo-structure.md)構造体の *m_nType* メンバーを参照してください。 詳細については、DAO ヘルプの「Type プロパティ」を参照してください。

*m_varValue*<br/>
[COleVariant](../../mfc/reference/colevariant-class.md)オブジェクトに格納されているパラメーターの値。

## <a name="remarks"></a>解説

上のプライマリとセカンダリへの参照は、クラスの [Getparameterinfo](../../mfc/reference/cdaoquerydef-class.md#getparameterinfo) メンバー関数によって情報がどのように返されるかを示し `CDaoQueryDef` ます。

MFC では、DAO パラメーターオブジェクトはクラスにカプセル化されません。 DAO querydef オブジェクトの基 `CDaoQueryDef` になる MFC オブジェクトは、パラメーターコレクションにパラメーターを格納します。 [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md)オブジェクト内のパラメーターオブジェクトにアクセスするに `GetParameterInfo` は、特定のパラメーター名またはインデックスをパラメーターコレクションに対して、querydef オブジェクトのメンバー関数を呼び出します。 [CDaoQueryDef:: GetParameterCount](../../mfc/reference/cdaoquerydef-class.md#getparametercount)メンバー関数をと組み合わせて使用し `GetParameterInfo` て、Parameters コレクションをループ処理することができます。

[CDaoQueryDef:: GetParameterInfo](../../mfc/reference/cdaoquerydef-class.md#getparameterinfo)メンバー関数によって取得された情報は、構造体に格納され `CDaoParameterInfo` ます。 `GetParameterInfo`パラメーターオブジェクトが格納されているパラメーターコレクションを持つ、の querydef オブジェクトに対してを呼び出します。

> [!NOTE]
> パラメーターの値のみを取得または設定する場合は、クラスの [GetParamValue](../../mfc/reference/cdaorecordset-class.md#getparamvalue) および [SetParamValue](../../mfc/reference/cdaorecordset-class.md#setparamvalue) メンバー関数を使用し `CDaoRecordset` ます。

`CDaoParameterInfo` は、 `Dump` デバッグビルドでメンバー関数も定義します。 を使用すると、 `Dump` オブジェクトの内容をダンプでき `CDaoParameterInfo` ます。

## <a name="requirements"></a>要件

**ヘッダー:** afxdao

## <a name="see-also"></a>関連項目

[構造体、スタイル、コールバック、およびメッセージマップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CDaoQueryDef クラス](../../mfc/reference/cdaoquerydef-class.md)
