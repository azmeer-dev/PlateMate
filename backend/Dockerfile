FROM public.ecr.aws/lambda/python:3.12

# Install dependencies first for optimal caching
COPY requirements.txt ${LAMBDA_TASK_ROOT}/
RUN python -m pip install --upgrade pip && \
    pip install -r requirements.txt --target "${LAMBDA_TASK_ROOT}"

# Copy application code after dependencies
COPY app/ ${LAMBDA_TASK_ROOT}/

# Set Lambda entry point
CMD ["app.lambda_handler"]
