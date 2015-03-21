# Alipay
对支付宝支付的二次封装，支持pc端和wap端支付

pay(pc):
	var orderNo = ""; //订单号
	var subject = ""; //订单名称
	var fee = 0.ToString("0.##"); //付款金额
	var notifyUrl = "host/Alipay/NotifyUrl.aspx";
	var returnUrl = "host/Alipay/ReturnUrl.aspx";
	var show_url = "host";
	var alipay = new Alipay.Submit();
	alipay.Pay(orderNo, subject, fee, body, notify_url, return_url, show_url);

pay(wap):
	var orderNo = ""; //订单号
	var title = "在线捐赠(WAP)：" + ""; //订单名称
	var fee = 0.ToString("0.##"); //付款金额
	var notifyUrl = "host/Alipay/NotifyUrl.aspx";
	var returnUrl = "host/Alipay/ReturnUrl.aspx";
	var show_url = "host";
	var alipay = new Alipay.Submit();
	alipay.Submit.Pay(orderNo, subject, fee, body, notify_url, return_url, show_url);

return(pc):
	public partial class NotifyUrl : Alipay.NotifyPage
	{
            protected override void OnNotifyConfirm()
            {
                //todo:业务逻辑处理
            }
	}

return(wap):
	public partial class NotifyUrl : Alipay.Wap.NotifyPage
	{
            protected override void OnNotifyConfirm()
            {
                //todo:业务逻辑处理
            }
        }
