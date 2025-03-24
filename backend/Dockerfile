# AWS Lambda Python 3.12 base image
FROM public.ecr.aws/lambda/python:3.12

# Copy backend application code into Lambda's working directory
COPY app/ ${LAMBDA_TASK_ROOT}

# Copy requirements.txt and install dependencies
COPY requirements.txt .
RUN python -m pip install --upgrade pip && \
    pip install -r requirements.txt --target "${LAMBDA_TASK_ROOT}"

# Command Lambda will use to start your application
CMD ["app.lambda_handler"]
