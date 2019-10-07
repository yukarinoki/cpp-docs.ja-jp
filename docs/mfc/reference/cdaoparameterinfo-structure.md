---
title: CDaoParameterInfo 構造体
ms.date: 09/17/2019
f1_keywords:
- CDaoParameterInfo
helpviewer_keywords:
- CDaoParameterInfo structure [MFC]
- DAO (Data Access Objects), Parameters collection
ms.assetid: 45fd53cd-cb84-4e12-b48d-7f2979f898ad
ms.openlocfilehash: 4f0ee7ebe1d5d4eff50194c2d5c5cccf8f373c61
ms.sourcegitcommit: 2f96e2fda591d7b1b28842b2ea24e6297bcc3622
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2019
ms.locfileid: "71096077"
---
# <a name="cdaoparameterinfo-structure"></a>CDaoParameterInfo 構造体

構造`CDaoParameterInfo`体には、データアクセスオブジェクト (DAO) 用に定義されたパラメーターオブジェクトに関する情報が含まれています。
DAO 3.6 は最終バージョンであり、互換性のために残されているものと見なされます。


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
パラメーターオブジェクトのデータ型を示す値です。 使用可能な値の一覧については、 [CDaoFieldInfo](../../mfc/reference/cdaofieldinfo-structure.md)構造体の*m_nType*メンバーを参照してください。 詳細については、DAO ヘルプの「Type プロパティ」を参照してください。

*m_varValue*<br/>
[COleVariant](../../mfc/reference/colevariant-class.md)オブジェクトに格納されているパラメーターの値。

## <a name="remarks"></a>Remarks

上のプライマリとセカンダリへの参照は、クラス`CDaoQueryDef`の[getparameterinfo](../../mfc/reference/cdaoquerydef-class.md#getparameterinfo)メンバー関数によって情報がどのように返されるかを示します。

MFC では、DAO パラメーターオブジェクトはクラスにカプセル化されません。 DAO querydef オブジェクトの基`CDaoQueryDef`になる MFC オブジェクトは、パラメーターコレクションにパラメーターを格納します。 [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md)オブジェクト内のパラメーターオブジェクトにアクセスするには、特定のパラメーター `GetParameterInfo`名またはインデックスをパラメーターコレクションに対して、querydef オブジェクトのメンバー関数を呼び出します。 [CDaoQueryDef:: getparametercount](../../mfc/reference/cdaoquerydef-class.md#getparametercount)メンバー関数をと`GetParameterInfo`組み合わせて使用して、Parameters コレクションをループ処理することができます。

[CDaoQueryDef:: getparameterinfo](../../mfc/reference/cdaoquerydef-class.md#getparameterinfo)メンバー関数によって取得された情報`CDaoParameterInfo`は、構造体に格納されます。 パラメーター `GetParameterInfo`オブジェクトが格納されているパラメーターコレクションを持つ、の querydef オブジェクトに対してを呼び出します。

> [!NOTE]
>  パラメーターの値のみを取得または設定する場合は、クラス`CDaoRecordset`の[GetParamValue](../../mfc/reference/cdaorecordset-class.md#getparamvalue)および[SetParamValue](../../mfc/reference/cdaorecordset-class.md#setparamvalue)メンバー関数を使用します。

`CDaoParameterInfo`は、 `Dump`デバッグビルドでメンバー関数も定義します。 を使用`Dump`すると、 `CDaoParameterInfo`オブジェクトの内容をダンプできます。

## <a name="requirements"></a>必要条件

**ヘッダー:** afxdao

## <a name="see-also"></a>関連項目

[構造体、スタイル、コールバック関数とメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CDaoQueryDef クラス](../../mfc/reference/cdaoquerydef-class.md)
