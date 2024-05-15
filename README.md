from email.message import EmailMessage
import ssl
import smtplib

email_sender = 'mikehoward23463@gmail.com'
email_password = 'yigk wlrk pctr envo'
email_receiver = 'gonzaloluchett9584@gmail.com'

subject = 'Am here waiting'
body = """
Hello how are you doing today please where is my money 
"""

em = EmailMessage()
em['From'] = email_sender
em['To'] = email_receiver
em['Subject'] = subject
em.set_content(body)

context = ssl.create_default_context()

with smtplib.SMTP_SSL('smtp.gmail.com', 465, context=context) as smtp:
    smtp.login(email_sender, email_password)
    smtp.sendmail(email_sender, email_receiver, em.as_string())
